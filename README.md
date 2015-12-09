# codeigniter-magento-style-view-path-hints
Magento style view path hints for codeigniter.

clone this project outside your codeigniter working directory, and copy the contents of the folder inside the root of your project. The files should copy themselves in the right places.

Adds a startdiv.php and enddiv.php viewfile to the application/view folder and overloads the codeigniter loader.php file with a slightly modified version that transforms the view($arg1,$arg2,$arg3) function insider the ci_loader class into view2($arg1,$arg2,$arg3).
Then the view function is redefined as a series of view2 calls as shown:

	public function view($view, $vars = array(), $return = FALSE)
	{	 $x = ['view' =>$view];
		 $this->view2('startdiv',$x);
		 $this->view2($view,$vars,$return);
		 $this->view2('enddiv');
	}
	
The startdiv and enddiv views is basically a wrapper div that creates pizel sized borders around each view call and reveal at a glance what would have essentially taken beginners at least a few hours of digging through code. 

Significantly reduces frustration during development and increases productivity. Replacing the Loader.php file with codeigniter's original loader.php file restores original functionality. 

A much simpler hack would be to interchange the function declaration names view and view2. 

Before: https://drive.google.com/file/d/0B1CPfDa5OHrNWWZSZlE5OGthZWs/view?usp=sharing

After: https://drive.google.com/file/d/0B1CPfDa5OHrNV3V6ZTZtQm9LVlE/view?usp=sharing

What it loks like in magento: https://www.google.com/search?tbm=isch&q=magento+template+path+hints (Pick one... IDK)

Currently Version 0.0.1
