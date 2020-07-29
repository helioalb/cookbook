# Wordpress

## How to know block attributes

```javascript
console.log(wp.blocks.getBlockType( 'core/button' ).attributes)
```

## How to know attributes to remove a hook (with example)

```php
    $hook_name = 'genesis_header';
    global $wp_filter;
    var_dump( $wp_filter[$hook_name] );
```

output

```
object(WP_Hook)#4335 (5) {
  ["callbacks"]=>
  array(3) {
    [5]=>
    array(1) {
      ["genesis_header_markup_open"]=>
      array(2) {
        ["function"]=>
        string(26) "genesis_header_markup_open"
        ["accepted_args"]=>
        int(1)
      }
    }
    [10]=>
    array(1) {
      ["EnglishPage::foo"]=>
      array(2) {
        ["function"]=>
        array(2) {
          [0]=>
          string(11) "EnglishPage"
          [1]=>
          string(3) "foo"
        }
        ["accepted_args"]=>
        int(1)
      }
    }
    [15]=>
    array(1) {
      ["genesis_header_markup_close"]=>
      array(2) {
        ["function"]=>
        string(27) "genesis_header_markup_close"
        ["accepted_args"]=>
        int(1)
      }
    }
  }
  ["iterations":"WP_Hook":private]=>
  array(0) {
  }
  ["current_priority":"WP_Hook":private]=>
  array(0) {
  }
  ["nesting_level":"WP_Hook":private]=>
  int(0)
  ["doing_action":"WP_Hook":private]=>
  bool(false)
}
```

for this :point_up: output use the code below:

```php
    remove_action( 'genesis_header', 'genesis_header_markup_open', 5);
    remove_action ( 'genesis_header', 'genesis_header_markup_close', 15);
    remove_action( 'genesis_header', array( 'EnglishPage', 'foo'), 15);
```
