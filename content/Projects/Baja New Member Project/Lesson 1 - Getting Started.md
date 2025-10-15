---
title: "Lesson 1: Getting Started with Baja Software"
---
In order to do all the things you’ll need to do on Baja, you’ll need to first understand what we do, why we do it, and install the software required.

## Intro to Baja - Software Mission

Let’s talk about why the electronics team exists. The electronics team was created around 2019 to support the development of the ECVT, our in-house automatic transmission. It was also created to support data collection for mechanical subteams, which then use that collected data to drive their designs.


Nowadays, after much growth and development, we can summarize the mission of the electronics team with a few key bullet points:
- Provide vehicle telemetry and data.
- Use data analysis to provide insights into mechanical subsystems.
- Support the software and logic for various electromechanical systems on the car.
- Push our boundaries of engineering to gain a competitive advantage.

## Software Stack

To accomplish this mission, we make use of various technologies. All these technologies, how to download them, and resources for them (if available) are detailed below. I can help troubleshoot most installation quirks with the big 3 operating systems (Windows, Linux, MacOS), as I have decent experience with all 3 of them. So, please let me know if you run into any issues.

### Google Drive

It may sound silly, but Google Drive is a large part of our software stack. Because we’re affiliated with the school, we get access to large Google Drive storage, allowing us to unify our club’s knowledge across subteams, and years! You can add Google Drive to your desktop for ease of use (it will show up as a normal folder). The process to do that [is detailed here](https://support.google.com/drive/answer/10838124?hl=en).


### Visual Studio Code

Visual Studio Code is a lightweight and extremely flexible text editor that serves as the backbone of our software stack. You’ll find that VSC is commonly used across the industry for software development due to its speed, ease of use, and flexibility.

You can [download Visual Studio Code here](https://code.visualstudio.com/download). Visual studio code comes with a number of extensions, which provide the actual code editing capabilities. Without those, VSC is just a text editor. Here are a few extensions that are useful:

- Platform IO (More on this soon)
- Better Markdown
- C++
- Python
- Rainbow CSV

### Platform IO
Let’s talk more about Platform IO. Platform IO (which I will call PIO from now on), is a build system that allows one to compile C++ code for microcontrollers. It’s extensible, and easily supports compiling to multiple CPU architectures with relative ease. You will probably be spending most of your time on the team working with PIO, as it compiles the code to run the microcontrollers on the car.

PIO also supports monorepos, where multiple build targets exist inside a single project folder. Monorepos allow for the consolidation of key infrastructure and parameters without cumbersome replication. In addition, it supports unit testing, where modules of code can be tested in isolation.

## Anaconda/Miniconda

Anaconda and Miniconda is a python package manager. Python is different from other programming languages in that you install packages to an environment to include libraries. Each virtual environment you create can have different packages and versions. However, this system can become cluttered very quickly, since each project/analysis you do has to have its own package folder. Over time the storage space this takes up can become cumbersome. 

Instead, we can use a lightweight package manager like miniconda (anaconda just comes with a GUI and some features that we won’t need) to keep track of our packages across our system. We can also invoke a python virtual environment easily from anywhere in our file system with a two word command. This makes our computer much less cluttered and package management much simpler. 

[Install Miniconda here](https://www.anaconda.com/docs/getting-started/miniconda/install).

### Waveforms (Digilent)
Waveforms is the software that we use to interface with our Analog Discovery 2 (AD2), the AD2 is an oscilloscope, logic analyzer, and function generator in a small, portable package. Because we work so much with hardware, we use the AD2 to troubleshoot hardware problems, and even simulate sensor inputs to our hardware for testing!

[Download waveforms here](https://digilent.com/reference/software/waveforms/waveforms-3/start). It sucks, but you will need to make an account.

### Altium and Solidworks
You will need to use Altium if you need to reference our PCBA schematics. You’ll need to use Solidworks if you ever need to find out the precise dimensions of something mechanical on the car. If you need either one, please come to me for further installation instructions.

## Good Software Development Process

Now let’s talk about good software development. Many of you have probably written code. Fewer of you have probably written code with a group. Fewer still have written code with a group, with pull requests (more on this later), and to production code standards. Thus, before you can start contributing to our code, let’s talk about some good practices.

### Self Documenting Code
You may have heard the phrase “good code is self documenting”. This essentially means that when another developer reads your code, they should be able to understand what your code is doing with little, or no comments.

Let’s do a quick little example. Imagine I have the following code:

  
```cpp
int convert_to_speed(int num){
	return 3.1672e-6 * num
}
```  

And compare that to this code, which is much more interpretable:

```cpp
int secondary_rpm_to_vehicle_mph(int secondary_rpm){  
	/* Conversion constant calculation is found in "constants.txt" */  
	int conversion_constant = 3.1672e-6;  
	return secondary_rpm * conversion_constant;  
}
```

So, by naming our functions and variables descriptively, we can have our code “document itself”, making it easier for the next person to work with your code.

### Test Coverage

Good code is also well tested! We’ll cover writing unit tests in a different lesson, but for now, let’s cover the overarching fundamentals.

To write a good unit test, you must test your code not only under normal operating conditions, but also under failures and test cases. You should understand how your code outputs for every given input. Code is good because code is deterministic. Meaning, you always know what it’s going to do.

If you have anything that’s not easily documented in code, or deserves more justification, you should write separate documentation. The same goes for blocks of code you write. If you create a class, you should write documentation for that class that details how it should be used and its behavior. One of the strengths of object oriented programming is that you can easily compartmentalize functionality, so the next programmer doesn’t need to care how it works, but only needs to care about inputs and outputs to your system.

[Google’s Style Guide to Writing Good C++](https://google.github.io/styleguide/cppguide.html)

## Understanding Scope and Reading a Ticket

The first thing that we must do when reading a ticket, or starting any task is to understand the requirements. What exactly is the ticket asking for?

From there, you must also become proficient at estimating time. Based on the scope of work from the previous step, how long do you think it’ll take you as a developer to implement the ticket? Leadership and management depends on accurate estimation to formulate their timelines. Also, giving accurate time estimates reduces the burden on you, the developer.

Understand your system well enough to scrutinize the design requirements and understand the details of what you have to do. If the requirements/goals of the ticket are bad in the first place, you should be comfortable enough to push back on them and refactor/reformat them. It’s your responsibility as the engineer to call out things that could be potential pitfalls and remedy them!

## The PR Process
A PR, or pull request, is the process by which your code is reviewed by another engineer, before it’s pulled into the main branch. A PR system is essential to prevent us from making silly mistakes. 

It’s often that one person, especially the person implementing the change, doesn’t see the issue with their code. Someone with fresh eyes is much more likely to see small issues. PRs can also help loop in relevant parties to changes that may impact their modules/systems.

Prepare for a PR by making your code easy to read, and squashing your commit history. After that, you can push your code to PR. This will make the reviewer’s life much easier. It’s also generally a good idea to give the code a sweep yourself before sending it to someone else.

It’s good etiquette in a PR to consolidate PR changes into waves of commits. So on your first round of PR, you squash all your changes into a new commit called “PR CHANGES 1” or something.

## Your First Ticket!
Now, it's time y'all to pick your first ticket!