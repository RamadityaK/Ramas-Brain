Geometric optics bend and shape light through the use of reflective and refractive elements (read [[The Nature of Light]] to learn more about the fundamental principles behind how these work). Below are some common optical elements and their properties and effects on images. 
## Plane Mirrors
![[Pasted image 20230905144157.png]]
In the above example of a plane mirror, light reflects off the mirror and goes to the observer's eyes. Interestingly, while the **object** is right under the observer, the **image** that you see through the mirror seems to be coming from within the mirror.
	
Such an image is called a **virtual image** because it cannot be projected onto a screen. If you walk behind the mirror the image will not exist. In contrast, some optical elements create **real images**, which can be projected onto a screen!
	
A plane mirror has an interesting property where
$$d_o = -d_i$$
The distance from the mirror to the object ($d_o$) is **equal and opposite to** the distance from the mirror to the image ($d_i$). Using this fact, we can reconstruct an object from an image and vice versa by applying this to every single point on the object.
![[Pasted image 20230905144932.png]]
Objects can also reflect more than once to create multiple images!
![[Pasted image 20230905145000.png]]
The expression for the number of images n formed due to two plane mirrors inclined at an angle $\theta$ is
$$n = \frac{360 \deg}{\theta} - 1$$

## Curved Mirrors
Curved mirrors differ from planar mirrors in that they can distort and displace objects in more ways than the single dimension that a planar mirror can. We will focus on two kinds of mirrors:
1. **Concave**: Forms a cave for the light (inner radius reflective).
2. **Convex:** Looks like a shield against the light (outer radius reflective).

### The Focal Point for a Curved Mirror
The symmetric axis of a curved mirror is called the **optical axis**. On this optical axis lie 
1. **Focal point:** Where all the incoming light rays converge. 
2. **Vertex:** The point where the optical axis and the lens intersect.
![[Pasted image 20230905145927.png]]
With these two definitions, we can define a critical quantity, called the **focal length**. The focal length is the distance from the vertex to the focal point!

	NOTE: The focal point can occur behind or in front of the mirror! Thus, it's very critical to use the PROJECTION of the reflected rays to determine where they converge (the projection means you continue the line in both directions to infty).

![[Pasted image 20230905150006.png]]
For a curved mirror the focal length is simply:
$$f = \frac{R}{2}$$

	NOTE: In the derivation of this formula, the small angle approximation was used. This means that this formula holds valid for curved mirrors where the distance that rays travel is much smaller than the curvature of the mirror.

### Geometric Ray Tracing for Curved Mirrors:
Ray tracing is a technique that we can use to determine the position of an image after an object's interaction with a mirror.
![[Pasted image 20230905115749.png]]
![[Pasted image 20230905150416.png]]
In the two images above, there are 4 principle rays that must be analyzed to determine where an image is. These rays are as follows:
1. **P-ray:** Parallel ray; comes in parallel to the optical axis.
2. **F-ray:** Focal ray; proceeds from/towards focal point $F_1$ and becomes parallel to the optical axis.
3. **V-ray:** Vertex ray; incident on vertex of mirror/lens, reflects off at the same angle from which it came (symmetry about the optical axis).
4. **C-ray:** Center-of-curvature ray; proceeds from/towards center of curvature. This ray reflects back from where it came!
### Critical Equations for Curved Mirrors:
The mirror equation is given by:
$$\frac{1}{d_o} + \frac{1}{d_i} = \frac{1}{f}$$
where $s$ is the distance of the object image, $s'$ is the image distance and $f$ is the focal length.

	NOTE: The focal length is positive for concave mirrors, and negative for convex mirrors! The image distance is positive for real images and negative for virtual images!

Another form of this equation is:
$$\frac{n_1}{d_o} + \frac{n_2}{d_i} = \frac{n_2-n_1}{R}$$
Where n is the index of refraction of the materials and R is the radius of curvature. We can also solve for the magnification
$$m = \frac{h_i}{h_o} = -\frac{d_i}{d_o}$$
where $h_i$ is the image height, $h_o$ is the object height, and m is the magnification. If $|m| > 1$, the image is enlarged. If $|m| < 1$, the image is shrunk. If $m < 0$, the image is inverted. If $m > 0$, the image is upright.
	
Sign conventions in optics can be tricky and important, so here is a helpful graphic:
![[Pasted image 20230905124701.png]]
^ **THESE ARE VERY IMPORTANT**

## Images formed by Refraction:
Often times in real life (most notably when looking into water), we encounter images that are distorted and shifted by refraction. Such an example is presented below:
![[Pasted image 20230905151835.png]]
Consider the rays from the point P, when they get refracted and reach our eyes, the refracted rays make it seem as if the object is at point Q! The depth that we "see" is called **the apparent depth**: $h_i$ (the height of the image). The actual depth of point p is the object height $h_0$. We can use the small angle approximation for a "normal viewing angle" and derive the following formula:
$$h_i = \frac{n_2}{n_1} h_0$$


## Thin Lenses
Lenses are perhaps the most useful/most used optical devices in instrumentation today! There are two main classes of lenses:
1. **Convex or Converging:** All light rays that enter it parallel to the optical axis intersect or focus at a single point on the optical axis on the opposite side of the lens.
2. **Concave or Diverging:** All rays that enter parallel to the optical axis diverge from the focal point.     
![[Pasted image 20230905152925.png]]

	NOTE: A lens is considered to be "thin" if the thickness is much less than the radii of the curvature of both surfaces. This allows us to assume that the light rays are bent only once at the center of the lens.

![[Pasted image 20230905122848.png]]
Converging lenses have **positive focal lengths**. They take parallel rays of light and converge them onto a single point. This point where they converge, this point is called $F_2$! The point where they are diverging is called $F_1$.

![[Pasted image 20230905122857.png]]
Diverging lenses have **negative focal lengths**. They take parallel rays of light and diverge them from the focal point. This point where they converge, this point is called $F_2$! The point where they are diverging is called $F_1$.

	NOTE: The locations of F2 and F1 are flipped from the convention for converging lenses. This is to keep with the convention that F1 is the place where they are diverging and F2 is the place where they are converging.

### Ray Tracing Rules for Thin Lenses:
The ray tracing rules are different for thin lenses than they are for curved mirrors!
1. **P-ray**: Starts parallel to the optical axis and goes through the focal point $F_2$ after the lens.
2. **V-ray**: Goes through the center of the lens and does not deviate from its course.
3. **F-ray**: Goes towards $F_1$ to begin and ends up parallel to the optical axis after lens. 

![[Pasted image 20230905153225.png]]
#### Oblique Parallel Rays and The Focal Plane:
![[Pasted image 20230905154140.png]]
If the rays incoming are not parallel to the optical axis, they do not converge at the focal point, but instead on the focal plane, which is perpendicular to the optical axis and intersects the focal point (shown above).
### Thin Lens Equations:
Thin lens equations are surprisingly similar to those for curved mirrors, but differ in a few key areas! For a thin lens:
$$\frac{1}{d_0} + \frac{1}{d_i} = \frac{1}{f}$$
We can also take this further to find a special equation called the **lens maker's equation**, which is defined as follows:
$$\frac{1}{f} = \left( \frac{n_2}{n_1} - 1 \right)\left( \frac{1}{R_1} -\frac{1}{R_2}\right)$$

The magnification is as follows:
$$m = \frac{h_i}{h_o} = -\frac{d_i}{d_o}$$
1. If $m>0$, then the image has the same vertical orientation as the object (called an “upright” image). 
2. If $m<0$, then the image has the opposite vertical orientation as the object (called an “inverted” image).
#### Sign Conventions for Thin-Lens Equations:
1. $d_i$ is positive if the image is on the side opposite the object (real image); otherwise, $d_i$ is negative (virtual image).
2. $d_o$ is positive and real if the light rays come **from** the object side. $d_o$ is negative and virtual if the light rays **don't come from** the object's side.
3. $f$ is positive for a converging lens and negative for a diverging lens.
4. $R$ is positive for a surface convex toward the object, and negative for a surface concave toward object.
5. $h_i$ is positive for upright (virtual images) and negative for inverted (real images).