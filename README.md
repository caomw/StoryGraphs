StoryGraphs
===========

This is a Matlab implementation of the paper:

----
StoryGraphs: Visualizing Character Interactions as a Timeline  
Makarand Tapaswi, Martin Bäuml, and Rainer Stiefelhagen  
IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2014  
[Project page](https://cvhci.anthropomatik.kit.edu/~mtapaswi/projects/storygraphs.html) | [download](https://cvhci.anthropomatik.kit.edu/~mtapaswi/papers/CVPR2014.pdf)

----

This project was inspired by the famous webcomic XKCD, in particular the [narrative charts](http://xkcd.com/657/).


### Tested on
Ubuntu 12.04, Ubuntu 14.04, with Matlab versions: R2013b and R2014a.  
I haven't tried with the new graphics engine on Matlab R2014b and <code>draw_storygraphs.m</code> may need some changes.


### First initialization
The <code>first_init.m</code> script will be called on running <code>startup.m</code> the first time. This will ask you to install two external toolboxes. Please follow the instructions.

---
### Example usage
<code>VS = BBT(1, 1);</code>  
<code>SG = storygraph(VS);</code>

Currently supported with ground-truth face identification for two TV series
- <em>The Big Bang Theory</em> ([BBT](http://en.wikipedia.org/wiki/The_Big_Bang_Theory)) season 1, episodes 1 -- 6
- <em>Buffy the Vampire Slayer</em> ([BUFFY](http://en.wikipedia.org/wiki/Buffy_the_Vampire_Slayer)) season 5, episodes 1 -- 6

They can be automatically generated by calling the script <code>cameraready_draw_sg.m</code>.  Line 70 <code>runexp = 1;</code> controls which experiment is performed.

----
### External toolboxes
- [jsonlab](http://www.mathworks.com/matlabcentral/fileexchange/33381-jsonlab--a-toolbox-to-encode-decode-json-files-in-matlab-octave): Matlab JSON interface
- [export_fig](http://mathworks.com/matlabcentral/fileexchange/23629-export-fig): (Optional) Save generated StoryGraphs
- [xticklabel_rotate](): Rotate figure XTick labels (Matlab R2014b onwards has inbuilt support!)



### Main functions
- [storygraph.m](blob/master/story/storygraph.m)   Generates the StoryGraph for video
- [storygraph_objective.m](blob/master/story/storygraph_objective.m)   The main objective function with gradient computation
- [storygraph_optimization.m](blob/master/story/storygraph_optimization.m)   Optimization wrapper for Matlab's <code>fmincon</code>
- [draw_storygraph.m](blob/master/story/draw_storygraph.m)   StoryGraph drawing function (run directly to try with random data)
- [co_occurrence_scenes.m](blob/master/story/co_occurrence_scenes.m)   Character occurrence matrix for each scene of the video



### Changelog
- v0.1: First working implementation for BBT, BUFFY


