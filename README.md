# WordPress Login Page Custom Background

This code snippet allows you to easily **set a custom background image for your WordPress login page**. By default, the login page has a plain background. This modification lets you personalize your login screen with any image you choose, aligning it with your brand or website's aesthetics.

## Why use a custom login background?

* **Branding:** Reinforce your brand identity by using your company's imagery on the login page.
* **Personalization:** Make the login experience more visually appealing and unique.
* **Consistency:** Ensure the login page's design is consistent with the rest of your website's look and feel.

## Installation

There are two primary methods to implement this code:

### Method 1: As a Standalone Plugin (Recommended)

Creating a small, dedicated plugin is the most robust way to add this customization. It ensures your custom background remains active even if you switch themes.

1.  Create a new folder named `wp-login-background` inside your WordPress site's `wp-content/plugins/` directory.
2.  Inside this new folder, create a file named `wp-login-background.php`.
3.  Copy and paste the following code into `wp-login-background.php`:

    ```php
    <?php
    /**
     * Plugin Name: WordPress Login Page Custom Background
     * Description: Sets a custom background image for the WordPress login page.
     * Version: 1.0
     * Author: Your Name (Optional)
     */

    function my_login_page_custom_bg_image() {
        // --- IMPORTANT: Change this URL to your desired background image URL ---
        $bgImageUrl = '[https://wordpress.org/files/2024/04/photo-community-1.png](https://wordpress.org/files/2024/04/photo-community-1.png)';
        // -------------------------------------------------------------------

        echo '<style type="text/css">
                body {
                    background-image: url("' . esc_url($bgImageUrl) . '") !important;
                    background-size: cover !important;
                    background-position: center center !important;
                }
              </style>';
    }
    add_action( 'login_enqueue_scripts', 'my_login_page_custom_bg_image' );
    ?>
    ```

4.  **Important:** Remember to change the `$bgImageUrl` variable in the code above to the actual URL of the image you want to use as your background.
5.  Go to your WordPress admin dashboard, navigate to **"Plugins"**, and **activate** the "WordPress Login Page Custom Background" plugin.

### Method 2: Adding to your Theme's functions.php File

You can add this code directly to your active theme's `functions.php` file. **It's highly recommended to back up your `functions.php` file before making any changes.**

1.  Navigate to `wp-content/themes/YourThemeName/` (replace `YourThemeName` with the actual name of your active theme).
2.  Open the `functions.php` file.
3.  Add the following code to the end of the file (before the closing `?>` tag, if one exists):

    ```php
    function my_login_page_custom_bg_image() {
        // --- IMPORTANT: Change this URL to your desired background image URL ---
        $bgImageUrl = '[https://chopipan.art/wp-content/uploads/2024/12/12.jpg](https://chopipan.art/wp-content/uploads/2024/12/12.jpg)';
        // -------------------------------------------------------------------

        echo '<style type="text/css">
                body {
                    background-image: url("' . esc_url($bgImageUrl) . '") !important;
                    background-size: cover !important;
                    background-position: center center !important;
                }
              </style>';
    }
    add_action( 'login_enqueue_scripts', 'my_login_page_custom_bg_image' );
    ```

4.  **Important:** Remember to change the `$bgImageUrl` variable in the code above to the actual URL of the image you want to use as your background.

## Customization

To change the background image, simply update the URL in the `$bgImageUrl` variable within the code to your desired image URL. For best results, use a high-resolution image.

## Contributing

Contributions are welcome! If you have suggestions or improvements for this code, feel free to open a "Pull Request" or report a new "Issue."

## License

This project is licensed under the GPLv2 or later.
