# wordpress-menu-classes-solution
Add custom classes to default Wordpress menu ul, li and a tag

# Add class to menu div and ul
$args = array(
'container' => 'add menu div class here',
'menu_class' => 'add menu ul class here',
'menu' => 'add menu name or id here' 
);
//call the menu here with the above arguments
wp_nav_menu($args);

# Add Class To menu li.
add_filter('nav_menu_css_class', function ($classes) {
        $classes[] = 'nav-item';
        return $classes;
        }, 10, 4);

# Add Class To menu li a tag
add_filter('nav_menu_link_attributes', function ($atts, $item, $args) {
    $class = 'nav-link';
    $atts['class'] = $class;
    return $atts;
    }, 10, 3);

