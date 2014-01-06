<!--For clearing css cache -->
<link rel="stylesheet" type="text/css" href="<?php echo get_template_directory_uri(); ?>/style.css?<?php echo date('l jS \of F Y h:i:s A'); ?>" >
<!-- jQuery -->
   <script src="//ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
<?php //problem
function widget_img() {
		$dir = bloginfo( 'template_url' );
		$src = $dir.'/images/sep.png';
		$img = '<img src="'.$src.'" />';
		print $img;
}

?>
<?php get_header(); ?> <?php get_footer(); ?><?php bloginfo('name'); ?>
<p><?php bloginfo('name'); ?>. &copy; | All Rights Reserved.</p>


<?php if ( have_posts() ) : ?>
	<?php while ( have_posts() ) : the_post(); ?>
	
	
	<?php endwhile; ?>
        <?php else : ?>
				<?php get_404_template(); ?>
		<?php endif; ?>
		
		
		
<?php register_nav_menus( array(
	'header_menu' => 'Header Navigation Menu',
	'footer_menu' => 'Footer Menu'
) );

<?php wp_nav_menu(array('theme_location'  => 'header_menu', 'items_wrap'      => '<ul id="nav" class="%2$s">%3$s</ul>')); ?>


$args = array(
	'default-color' => '#050F32',
	'default-image' => get_template_directory_uri() . '/images/main_bg.jpg',
);
add_theme_support( 'custom-background', $args );


$args = array(
	'width'         => 960,
	'height'        => 300,
	'default-image' => get_template_directory_uri() . '/images/banner.jpg',
);
add_theme_support( 'custom-header', $args );
 ?>
 
 <img src="<?php header_image(); ?>" width="<?php echo get_custom_header()->width; ?>" height="<?php echo get_custom_header()->height; ?>" alt="<?php bloginfo('name'); ?>" />
 
<?php  
register_sidebar(array(
    		'name' => 'Left sidebar 1',
    		'id'   => 'sidebar-widgets1',
    		'description'   => 'Widgets for the left sidebar.',
    		'before_widget' => '',
    		'after_widget'  => '',
    		'before_title'  => '<h3>',
    		'after_title'   => '</h3><hr/>'
    	));
?>

<a href="<?php the_permalink() ?>"><h2><?php the_title(); ?></h2></a>
		<?php the_content(); ?>  
		
		
<?php if ( ! dynamic_sidebar( 'Left sidebar 2' ) ) : ?>
            <p></p>
<?php endif; ?> 

<?php  ?>
<?php  ?>



<meta name="description" content="<?php if ( is_single() ) {
			global $post;
			$key = "description";
        get_post_meta( $post->ID, $key, true );
    } else {
        bloginfo('name'); echo " - "; bloginfo('description');
    }
    ?>" />

stylesheet url

<link rel="stylesheet" type="text/css" media="all" href="<?php bloginfo( 'stylesheet_url' ); ?>" />


theme dir uri

<?php echo get_template_directory_uri(); ?>/

<?php echo bloginfo('template_directory'); ?>


<?php
  //for custom header
$args = array(
	'width'         => 960,
	'height'        => 300,
	'default-image' => get_template_directory_uri() . '/images/banner.jpg',
);
add_theme_support( 'custom-header', $args );

?>


  <?php 
  //for post thumbnails
	add_theme_support('post-thumbnails', array('post','page'));
	//for add image size
	add_image_size('post-image', 150, 150, true );
	add_image_size('single-post-image', 400, 300, true );
	//  add header image size for page;
	add_image_size('header-image', 960, 300, true );
  
  ?>

<?php ?>


<?php ?>

<?php ?>


  for header file
<?php
				
	// Check if this is a post or page, if it has a thumbnail, and if it's a big one

      if ( is_page() && is_singular() && current_theme_supports( 'post-thumbnails' ) &&
	       has_post_thumbnail( $post->ID ) &&
 
         ( /* $src, $width, $height */ $image = wp_get_attachment_image_src( get_post_thumbnail_id( $post->ID ), 'post-thumbnail' ) ) &&
	
          $image[1] >= HEADER_IMAGE_WIDTH ) :
	      // Houston, we have a new header image!
		
		  echo get_the_post_thumbnail( $post->ID );
	   elseif ( get_header_image() ) : ?>
					
	               <img src="<?php header_image(); ?>" width="<?php echo HEADER_IMAGE_WIDTH; ?>" height="<?php echo HEADER_IMAGE_HEIGHT; ?>" alt="" />
			
		<?php endif; ?>

		
		
		
<?php		
	//remove wp logo from admin bar	
function annointed_admin_bar_remove() {
        global $wp_admin_bar;

        /* Remove their stuff */
        $wp_admin_bar->remove_menu('wp-logo');
}

add_action('wp_before_admin_bar_render', 'annointed_admin_bar_remove', 0); 

?>



<?php 
  //add into admin bar site drop down menu 
	function ipstenu_admin_bar_add() {

        global $wp_admin_bar, $user_identity;

        $user_id = get_current_user_id();

 

        /* Add my stuff */

        if ( 0 != $user_id ) {

                $avatar = get_avatar( get_current_user_id(), 16 );

                $id = ( ! empty( $avatar ) ) ? 'ipstenu-account-with-avatar' : 'ipstenu-account';

                $wp_admin_bar->add_menu( array( 'id' => $id, 'title' => $avatar . $user_identity,  'href' => 'http://newshat.tk'. $user_identity .'/profile/' ) );

                $wp_admin_bar->add_menu( array( 'parent' => $id, 'title' => __( 'Edit My Profile' ), 'href' => 'http://newshat.tk'. $user_identity .'/profile/edit/' ) );

                if ( current_user_can('manage_options') ) {

                        $wp_admin_bar->add_menu( array( 'parent' => $id, 'title' => __( 'Dashboard' ), 'href' => 'http://newshat.tk/wp-admin/' ) );

                        $wp_admin_bar->add_menu( array( 'parent' => $id, 'title' => __( 'Network Admin' ), 'href' => 'http://newshat.tk/wp-admin/network' ) );

                }

                $wp_admin_bar->add_menu( array( 'parent' => $id, 'title' => __( '<strong>Log Out</strong>' ), 'href' => wp_logout_url() ) );

        }

}

 

add_action( 'admin_bar_menu', 'ipstenu_admin_bar_add', 10 );
 ?>
 

 
  <?php 
 
 /**
 * Dashboard widgets
 */
function custom_remove_dashboard_widgets() {
	global $wp_meta_boxes;
	unset( $wp_meta_boxes['dashboard']['side']['core']['dashboard_quick_press'] ); # Allows for basic post entry
	unset( $wp_meta_boxes['dashboard']['normal']['core']['dashboard_incoming_links'] ); # Shows you who is linking to you
	unset( $wp_meta_boxes['dashboard']['normal']['core']['dashboard_plugins'] ); # Displays new, updated, and popular WordPress plugins on WordPress.org
	unset( $wp_meta_boxes['dashboard']['side']['core']['dashboard_primary'] ); # Highlights entries from the WordPress team on WordPress.org
	# unset( $wp_meta_boxes['dashboard']['normal']['core']['dashboard_right_now'] ); # Displays stats about your blog
	# unset( $wp_meta_boxes['dashboard']['normal']['core']['dashboard_recent_comments'] ); # Displays the most recent comments on your blog
	# unset( $wp_meta_boxes['dashboard']['side']['core']['dashboard_recent_drafts'] ); # Displays your most recent drafts
	# unset( $wp_meta_boxes['dashboard']['side']['core']['dashboard_secondary'] ); # Displays the WordPress Planet feed, which includes blog entries from WordPress.org
}
add_action( 'wp_dashboard_setup', 'custom_remove_dashboard_widgets' );
 
 
 ?>
 
 
 
 
 
  <?php 
 
 function comment_scripts() {
    if (is_singular()) wp_enqueue_script('comment-reply');
		}
		
		add_action('wp_enqueue_scripts', 'comment_scripts');
 
 ?>
 
 
 
 Character Set:  					  bloginfo( 'charset' )
Home URL:		 						echo home_url()
HTML type:							 bloginfo( 'html_type' )
Feed Links:							 get_feed_link( 'feed' ) (where feed is rss, rss2, atom)
Language: 								bloginfo( 'language' ) (en-US)
Locale: 								get_locale() (en_US)
Parent Theme Directory URL:			 get_template_directory_uri()
Parent Theme Directory File Path: 		get_template_directory()
Parent Theme Name: 					get_template()
Site Description:					 bloginfo( 'description' )
Site Title: 						bloginfo( 'name' )
Style Sheet Directory URL: 			get_stylesheet_directory_uri()
Style Sheet URL: 				get_stylesheet_uri()
Theme Directory File Path: 		get_stylesheet_directory()
Text Direction: 				bloginfo( 'text_direction' )
WordPress URL: 					echo site_url()
WordPress Version: 				bloginfo( 'version' )
 
 <?php

// The Query
query_posts( $args );

// The Loop
while ( have_posts() ) : the_post();
	echo '<li>';
	the_title();
	echo '</li>';
endwhile;

// Reset Query
wp_reset_query();
<?php previous_posts_link(); ?>
<?php next_posts_link(); ?>

<?php
function catch_that_image() {
  global $post, $posts;
  $first_img = '';
  ob_start();
  ob_end_clean();
  $output = preg_match_all('/<img.+src=[\'"]([^\'"]+)[\'"].*>/i', $post->post_content, $matches);
  $first_img = $matches [1] [0];

  if(empty($first_img)){ //Defines a default image
    $first_img = "/images/default.jpg";
  }
  return $first_img;
}

?>
<?php echo catch_that_image() ?>
 
 substr(get_the_excerpt(), 0,50)
 
 function excerpt($num) {
		$limit = $num+1;
		$excerpt = explode(' ', get_the_excerpt(), $limit);
		array_pop($excerpt);
		$excerpt = implode(" ", $excerpt)."...";
		echo $excerpt;
	}
 
 
 // show full and excerpt together
 <?php if (have_posts()) :
    while (have_posts()) : the_post();
         $customField = get_post_custom_values("full");
       	 if (isset($customField[0])) {
              //Custom field is set, display a full post
              the_title();
              the_content();
         } else {
              // No custom field set, let's display an excerpt
              the_title();
              the_excerpt();
    endwhile;
endif;
?>
 
 <?php 
 // different sidebar for diff. page and page. sidebar-$sidebar
 $sidebar = get_post_meta($post->ID, "sidebar", true);
get_sidebar($sidebar);
?>
//Display Content Only To Registered Users
 <?php
 function member_check_shortcode($atts, $content = null) {
  if (is_user_logged_in() && !is_null($content) && !is_feed()) {
    return $content;
  } else {
    return 'Sorry, this part is only available to our members. Click here to become a member!';
}

add_shortcode('member', 'member_check_shortcode');
//Once that’s done, you can add the following to your posts to create a section or text (or any other content) 
//that will be displayed only to registered users:
[member]
This text will be displayed only to registered users.
[/member]
 ?>
 
 
 <?php 
 //admin header logo
add_action('admin_head', 'my_custom_logo');

function my_custom_logo() {
   echo '
      <style type="text/css">
         #header-logo { background-image: url('.get_bloginfo('template_directory').'/images/custom-logo.gif) !important; }
      </style>
   ';
}
 
 ?>
 
 
****custom search*****
 <form method="get" action="<?php bloginfo('url'); ?>">
		<fieldset>
		<input type="hidden" name="s" value="" placeholder="search&hellip;" maxlength="50" required="required" />
		Type : <select name="category_name">
				<?php
		// generate list of categories
		$categories = get_categories();
		foreach ($categories as $category) {
			echo '<option value="', $category->slug, '">', $category->name, "</option>\n";
		}
		?>
		</select>
		Price : <select name="tag">
				<?php
		// generate list of tags
		$tags = get_tags();
		foreach ($tags as $tag) {
			echo '<option value="', $tag->slug, '">', $tag->name, "</option>\n";
		}
		?>
		</select>
		<button type="submit">Search</button>
		</fieldset>
		</form>
****custom search*****


 <?php ?>
 <?php ?>
 <?php ?>
 
 background-image: -webkit-gradient(linear, left top, left bottom, from(#DA2D31), to(#F77F20));
background-image: -webkit-linear-gradient(top, #DA2D31, #F77F20);
background-image: -moz-linear-gradient(top, #DA2D31, #F77F20);
background-image: -ms-linear-gradient(top, #DA2D31, #F77F20);
background-image: -o-linear-gradient(top, #DA2D31, #F77F20);
background-image: linear-gradient(to bottom, #DA2D31, #F77F20);
