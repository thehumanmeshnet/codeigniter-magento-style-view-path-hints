# codeigniter-magento-style-view-path-hints
magento style view path hints for codeigniter. Significantly reduces frustration at development time and increases productivity. Replacing the Loader.php file with the original that came with codeigniter restores original functionality.


Loader.php originally contained a public function view($1,$2,$3) that I have augmented by means of public function view2($1,$2,$3) which basically renders a startdiv.php view before, and an enddiv.php view after running any view renders requested by the user.

interchanging the function declaration names view and view2 also disables the hints. 