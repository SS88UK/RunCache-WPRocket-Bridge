# RunCache & WP Rocket Bridge
When WP Rokcet clears it's cache, this plugin will also clear RunCache too.

```
add_action('after_rocket_clean_post', function( $post ) {
	if(class_exists('RunCache_Purger')) RunCache_Purger::flush_post($post->ID);
});


add_action( 'after_rocket_clean_domain', function() {
    if(class_exists('RunCache_Purger')) RunCache_Purger::flush_home(true);
});
```
