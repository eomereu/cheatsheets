# Wordpress Hand Notes
## Theme
**Astra** is a perfect choice for a clean start.

## Plugins
\* Needed for the websites which will have user functionality  
\*\* Needed for the websites which will have shop & online selling functionality  
\*\*\* Needed for restaurant like websites  
### Starter Templates | By Brainstorm Force
Enables us to import pre-made, pages, blocks etc.
   
### Yoast Duplicate Post | By Enrico Battocchi & Team Yoast
To clone Pages etc.
   
### \*WooCommerce | By Automattic
For shopping purposes
```css
/*__WOOCOMMERCE__START__*/
/* woocommerce Add to Cart button */
#place_order, button.single_add_to_cart_button.button.alt, .woocommerce-Button.button {
  border-radius: 5px !important;
  padding: 0.8rem 2rem !important;
  font-family: Lato, Helvetica, Arial, sans-serif;
  font-size: 16px;
  font-weight: 600;
  letter-spacing: 0px;
  text-transform: none;
  background-color: #E9D598 !important;
  border: none;
  color: black !important;
}
#place_order:hover, button.single_add_to_cart_button.button.alt:hover, .woocommerce-Button.button:hover {
  color: white !important;
  cursor: pointer;
  box-shadow: none !important;
  background-color: #E9D598 !important;
}
/* other woocommerce buttons */
.woocommerce a.button {
  color: black !important;
}
.woocommerce a.button:hover {
  background-color: #E9D598 !important;
  color: white !important;
}
/* hide additional informations on product page */
.wapf {
  display: none !important;
}
/* Increase hight of No Downloads Available Yet message in account page */
.woocommerce-Message.woocommerce-Message--info.woocommerce-info {
  height: 6rem;
}
/* editing quantity box */
.quantity input {
  box-shadow: inset 0px 0px 2px #000000;
  -webkit-box-shadow: inset 0px 0px 2px #000000;
  -moz-box-shadow: inset 0px 0px 2px #000000;
}
/* hide product images */
.thumbnails.thumbnails-ori, a.woocommerce-LoopProduct-link.woocommerce-loop-product__link img {
  display: none !important;
}
/* center title price etc. */
.woocommerce ul.products li.product a.woocommerce-loop-product__link {
  transition: all .21s cubic-bezier(.5,.5,.4,.9);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding-bottom: 2rem;
}
/* in Cart - coloring remove items bar */
td.product-remove {
  background: #E9D598 !important;
}
td.product-remove a {
  background: white !important;
}
/* on checkout sign up text addition */ 
.woocommerce-account-fields p label span::after {
  content: " (indem Sie den in den obigen 2 Checkboxen genannten Dokumenten zustimmen)";
}
/* give margin to chekout page etc. */
#page_content_wrapper .inner .sidebar_content.full_width, .page_content_wrapper .inner .sidebar_content.full_width {
  margin-bottom: 3rem;
}
/* return to shop button on empty cart and checkout page */
p.return-to-shop a {
  padding: 0.8rem 2rem !important;
}
/* hide product images on product pages */
.woocommerce-product-gallery {
display: none;
}
/* aligning product info to left */
.woocommerce #content div.product div.summary, .woocommerce div.product div.summary, .woocommerce-page #content div.product div.summary, .woocommerce-page div.product div.summary {
  float: left;
  width: 48%;
  clear: none;
  padding-left: 2rem;
  margin-top: 5rem;
}
/*__WOOCOMMERCE__END__*/
/*__TABLET__*/
/*__WOOCOMMERCE__*/
/* checkout page */
body.woocommerce-checkout .woocommerce .col2-set, body.woocommerce-checkout.woocommerce-page .col2-set {
  width: 100%;
}
body.woocommerce-checkout .woocommerce #order_review {
  float: left;
  width: 100%;
}
/* payment fields */
/* RE-INSPECT THIS CODE, THIS MAY NOT FIX PAYMENT FIELDS SINCE IT IS MODIFIED BECAUSE IT WAS BREAKING OTHER THINGS */
#page_content_wrapper .inner .sidebar_content.full_width img, .page_content_wrapper img, .page_content_wrapper iframe {
  height: 25px;
}
/* fixing category images */
/* PLEASE BEWARE THAT THIS CODE BREAKS THE IMAGES ON HOME PAGE! */
/* PROBABLY THERE WILL BE NO NEED FOR THIS CODE */
/*
#page_content_wrapper .inner .sidebar_content.full_width img {
  height: auto !important;
}
*/
/*__PHONE__*/
/*__WOOCOMMERCE__*/
/* editing woocommerce fields */
.woocommerce-Message.woocommerce-Message--info.woocommerce-info {
  display: flex;
  flex-direction: column-reverse;
  height: 119px;
}
.woocommerce-message.woocommerce-message--info.woocommerce-Message.woocommerce-Message--info.woocommerce-info {
  margin-top: 2rem;
}
.woocommerce-form-coupon-toggle {
  margin-top: 2rem;
}
/* woocommerce product title */
h2.woocommerce-loop-product__title {
  min-width: auto;
}
.quick-view-button {
  width: 100% !important;
  font-size: 15px;
}
/* get rid of padding and margin of product information */
.woocommerce #content div.product div.summary, .woocommerce div.product div.summary, .woocommerce-page #content div.product div.summary, .woocommerce-page div.product div.summary {
  padding-left: 0;
  margin-top: 2rem;
}
```
		
### \*Visibility Logic for Elementor | By StaxWP
To hide/show elements based on user roles (guests/signed in users etc.)
  
### \*User Menus | By Code Atlantic
To hide/show links in the Site Menu (i.e. in NavBar) based on user roles (guests/signed in users etc.)
  
### \*Extra Product Options for WooCommerce | By actpro *(Products -> Extra Product Addons)*
To add custom fields like "pizza-toppings" based on category or product with prices
  
### \*\*ELEX WooCommerce Catalog Mode | By ELEXtensions *(WooCommerce -> Catalog Mode)*
To hide "Add to Cart" button on Shop page.
 
### \*\*WPC Smart Quick View for WooCommerce | By WPClever
To add "Quick View" option to products on Shop page
```css
/*__QUICK_VIEW__START__*/
/* stylizing quick view window */
div#woosq-popup {
  border-radius: 15px;
  padding: 1rem 2rem;
  max-height: 80vh;
}
/* stylizing quick view button */
.quick-view-button {
  border-radius: 5px;
  padding: 0.8rem 2rem;
  font-family: Lato, Helvetica, Arial, sans-serif;
  font-size: 16px;
  font-weight: 600;
  letter-spacing: 0px;
  text-transform: none;
  background-color: #E9D598;
  border: none;
  color: black;
  /*width: 100%;*/
}
.quick-view-button:hover {
  color: white;
  cursor: pointer;
}
/* aligning pop up close icon */
.mfp-close:before {
  top: -23px;
  left: 5px;
  z-index: 2;
  transform: rotate(360deg) !important;
}
/* making summary part full width */
.woosq-product > .product {
flex-direction: column;
}
.woosq-product > .product > div {
  width: 100% !important;
}
/* editing toppings section text etc. */
.epofw_fields_table tr td label {
  display: flex;
  font-family: Lato, Helvetica, Arial, sans-serif;
  text-transform: capitalize;
  font-weight: 400;
  align-items: center;
  font-size: 100%;
  transform: scaleY(0.98);
}
.epofw_fields_table tr td:nth-child(odd) label {
  font-weight: 600;
}
/*__QUICK_VIEW__END__*/
/*__TABLET__*/
/*__QUICK_VIEW__*/
/* quick-view */
div#woosq-popup {
  padding: 1rem 0;
}
```
		
### WPS Hide Login | By WPServeur, NicolasKulka, wpformation *(Settings -> WPS Hide Login)*
To hide "/wp-admin/"
  
### \*MC4WP: Mailchimp for WordPress | By ibericode
Organize Newsletter things including the checkbox within "Contact Form 7", WoocCommerce Sign-up and WooCommerce Checkout
 
### Contact Form 7 | By Takayuki Miyoshi
For a good contact form, integration by MailChimp available
```css
/*__CONTACT_FORM__START__*/
/* form submit button */
.wpcf7-submit {
  background-color: #E9D598 !important;
  border-color: #E9D598 !important;
  color: black !important;
  width: 100%;
}
.wpcf7-submit:hover {
  color: white !important;
}
/*__CONTACT_FORM__END__*/

12.GDPR Cookie Consent | By WebToffee: To create a cookie pop-up
/*__COOKIE_CONSENT__START__*/
/* save and close button */
#wt-cli-privacy-save-btn {
  margin-bottom: 1rem;
  border-radius: 5px;
}
/* the cookie bar */
#cookie-law-info-bar {
  border-radius: 5px;
  width: auto;
  margin: 2rem;
}
/* buttons on the cookie bar */
.cli-bar-btn_container a {
  border-radius: 5px;
}
/*__COOKIE_CONSENT__END__*/
/*__TABLET__*/
/*__COOKIE_CONSENT__*/
/* Cookie bar buttons */
.cli-style-v2.cli-bar-container {
  justify-content: right;
}
/*__PHONE__*/
/*__COOKIE_CONSENT__*/
/* Cookie Save & Accept button */
#wt-cli-privacy-save-btn {
  font-size: 12px;
}
/* Cookie bar buttons */
.cli-style-v2 .cli-bar-btn_container {
  flex-wrap: nowrap;
}
/* einstellungen button */
a.medium.cli-plugin-button cli-plugin-main-button.cli_settings_button {
  font-size: 11px;
}
/* cookie message */
.cli-style-v2 .cli-bar-message {
  font-size: 12px;
}
```

### Contact Form 7 Captcha | By 247wd
Gives us a shortcode for cpatcha verification to add into Contact Form 7 in order to prevent bots.  
Tutorial video: *https://youtu.be/D8pmQRQnGbI*
		
### \*\*\*Quick Restaurant Reservations | By ThingsForRestaurants
For a reservation form and managing them, even for mailing
```css
/*__RESERVATION_FORM__START__*/
/* deleting borders of reservation form */
.qrr-booking-form fieldset {
  border: none;
}
/* stretching reservation form boxes */
#qrr-message, #qrr-party, #qrr-time, .qrr-text input {
  width: 100%;
}
/* stylizing reservation request button */
.qrr-submit button {
  border-radius: 5px;
  padding: 0.8rem 2rem;
  font-family: Lato, Helvetica, Arial, sans-serif;
  font-size: 16px;
  font-weight: 600;
  letter-spacing: 0px;
  text-transform: none;
  background-color: #E9D598;
  border: none;
  color: black;
}
.qrr-submit button:hover {
  color: white;
  cursor: pointer;
}
/* centering submit button */
.qrr-submit div {
  display: flex;
  justify-content: center;
}
/* stretching reservation button */
.qrr-submit button {
  width: 100%;
}
/* reservation date picker */
/* month, year, days */
#qrr-date_root .picker__month, #qrr-date_root .picker__year, #qrr-date_table .picker__weekday {
  font-weight: 600;
  color: black;
}
/* prev and next month indicators */
#qrr-date_root .picker__nav--prev:before, #qrr-date_root .picker__nav--next:before {
border-left-color: blue;
  border-right-color: blue;
}
/* disabled days */
#qrr-date_table .picker__day--disabled, #qrr-date_table .picker__day--disabled:hover, #qrr-date_table .picker--focused .picker__day--disabled {
  background: #E9D598;
  color: white;
  font-weight: 600;
}
/* available days in current month */
.picker__day.picker__day--infocus {
  font-weight: 600;
}
/* available days in next month */
.picker__day.picker__day--outfocus {
  font-weight: 600;
}
/* keymap */
#qrr-date_root .picker__button--today, #qrr-date_root .picker__button--clear, #qrr-date_root .picker__button--close {
  font-weight: 600;
}
/*__RESERVATION_FORM__END__*/
/*__PHONE__*/
/*__RESERVATION_FORM__*/
/* Editing Reservation Request button */
.qrr-submit button {
  font-size: 13px;
}
/* stretching reservation form boxes */
#qrr-message, #qrr-party, #qrr-time, .qrr-text input {
  height: 35px;
}
/* making message box bigger */
#qrr-message {
  height: 145px !important;
}
/* reservation table days width */
#qrr-date_table .picker__weekday {
  padding: 0;
}
```
		
### ***Restaurant & Cafe Addon for Elementor | By NicheAddons
To create a perfect looking menu within Elementor
```css
/*__RESTAURANT_MENU__START__*/
/* stylizing items */
.narep-food-menu-item-wrap.zoom-image.food-menu-toggle.no-img {
  margin-bottom: 30px !important;
  padding: 0px !important;
  border: 0px !important;
  box-shadow: none !important;
}
/* fixing position of food prices */
.food-price {
  position: absolute !important;
}
/*__RESTAURANT_MENU__END__*/
/*__TABLET__*/
/*__RESTAURANT_MENU__*/
/* food title and price in menu */
.food-title, .food-price {
  line-height: 19px !important;
}
/*__PHONE__*/
/*__RESTAURANT_MENU__*/
/* food titles in Menu */
.food-title {
  width: 85%;
}
```
		
### Popup Maker | By Popup Maker
To create pop-ups (maybe during build of the website)
```css
/*__POP_UP__START__*/
/* stylizing pop-up window */
#popmake-7131 {
  padding: 15px 30px 30px 30px;
  margin-left: 5%;
  margin-right: 5%;
  width: 40vw !important;
}
/*__POP_UP__END__*/
/*__TABLET__*/
/*__POP_UP__*/
/* construction pop-up */
#popmake-7131 {
  width: 70vw !important;
}
/*__PHONE__*/
/*__POP_UP__*/
/* construction pop-up */
#popmake-7131 {
  width: 80vw !important;
}
/* construction pop-up heading */
#pum_popup_title_7131 {
  font-size: 30px;
}
/* construction pop-up text */
#popmake-7131 p {
  font-size: 15px;
}
```

### \*\*Mollie Payments for WooCommerce | By Mollie
Mobile Payments
```css
/*__MOLLIE__START__*/
/* tidying Ablaufdatum CVC/CVV sections */
.mollie-components #expiryDate {
  padding-right: 2%;
}
.mollie-components #verificationCode {
  padding-left: 2%;
}
.mollie-components #expiryDate, .mollie-components #verificationCode {
  max-width: 48%;
}
/*__MOLLIE__END__*/
```
		
### \*\*Ace Woo Ajax Cart Count | By AceWebX Team *(Settings -> Ace Cart Count)*
To print item count and/or price with Cart icon  
*ex icon:* `[fas fa-shopping-bag]`  
*id:* `#cart-on-n-header`
```css
/*__AJAX_CART_COUNT__START__*/
/* stylizing on all headers */
#cart-on-t-header, #cart-on-s-header, #cart-on-n-header {
  font-size: 17px;
  font-family: "Lato", Sans-serif;
  font-weight: 600;
  letter-spacing: 0px;
}
/* stylizing on transparent header */
#cart-on-t-header a {
  color: white;
}
#cart-on-t-header a:hover {
  color: #E9D598;
}
/*__AJAX_CART_COUNT__END__*/
```
**PHP File**  
*/home3/radfeube/public_html/wp-content/plugins/woo-ajax-cart-count/public/partials/ace-woo-ajax-cart-count-public-display.php*
```php
<?php

/**
  * Provide a public-facing view for the plugin
  *
  * This file is used to markup the public-facing aspects of the plugin.
  *
  * @link       https://profiles.wordpress.org/acewebx/#content-plugins
  * @since      1.0.0
  *
  * @package    Ace_Woo_Ajax_Cart_Count
  * @subpackage Ace_Woo_Ajax_Cart_Count/public/partials
  */
if (version_compare(WOOCOMMERCE_VERSION, '2.5.2', '>=')) {
  $cartURL = wc_get_cart_url();
} else {
  $cartURL = $woocommerce->cart->get_cart_url();
}
?>
<a class="cart-customlocation imsAjaxCartCount" style="font-size:<?php echo get_option('imsAjaxCartCount_optionFontSize'); ?>px; color:<?php echo get_option('imsAjaxCartCount_optionColor'); ?>;" href="<?php echo $cartURL; ?>">
  <i style="padding-right: 8px; transform: scale(1.5);" class="<?php echo get_option('imsAjaxCartCount_optionIcon'); ?>" aria-hidden="true"></i>
  <?php 
    if ($woocommerce->cart->cart_contents_count != 0) {
      echo $woocommerce->cart->get_cart_total();
    }
  ?>
</a>
```

### 404page - your smart custom 404 error page | By Peter Raschendorfer *(Appearance -> 404 Error Page)*
To specify 404 Error Page

### UpdraftPlus - Backup/Restore | By UpdraftPlus.Com, DavidAnderson *(Settings -> UpdraftPlus Backups)*
To automatically create backups and restore them in Google Drive etc.
  
### \*\*Checkout Field Editor for WooCommerce | By ThemeHigh *(WooCommerce -> Checkout Form)*
Enables us to edit, rearrange and add fields on/onto Checkout page. PS: Also can be used to add accepting AGB and Datenschutzerklärung checkboxes  
*i.e.* `Ich akzeptiere <a href="/privacy-policy/">Datenshutzerklärung</a>`

### Loco Translate | By Tim Whitlock
To translate everything like Plugins
  
### LoftLoader | By Loft.Ocean *(Settings -> LoftLoader Lite)*
To add an animated preloader to your website with fully customisations
  
### \*\*Shipping Zones by Drawing for WooCommerce | By Arosoft.se *(WooCommerce -> Shipping Zones by Drawing)*
Enables us to draw shipping zones. Requires Google Maps API Key.  
Tutorial video to get Google Maps API Key: *https://youtu.be/OGTG1l7yin4*

### \*\*Order Minimum/Maximum Amount for WooCommerce | By WPFactory *(WooCommerce -> Settings -> Order Min/Max Account)*
Enables to specify min/max quantity for orders.  
Tutorial video: *https://youtu.be/Eb6zJS__x6M*

### Redirection | By John Godley *(Tools -> Redirection)*
Redirects URLs
*i.e.* `/404` to `/page-not-found`

### GTranslate | By Translate AI Multilingual Solutions *(Settings -> GTranslate)*
Helps to change all site's language in one click
```css
/*__GTRANSLATE__START__*/
/* gtranslate hover and active colors */
/* "gtanslate-bar" class is assigned via Elementor */
.gtranslate-bar a:hover, .gtranslate-bar a:active {
  color: white !important;
}
/*__GTRANSLATE__END__*/
```
  
## CSS Breakpoints
### Tablet
```css
@media screen and (max-width: 1024px) {

}
```
### Phone
```css
@media screen and (max-width: 767px) {

}
```

## Additional Styling
```css
/*__GALLERY_SLIDER__START__*/
/* gallery slider on homepage, share etc. buttons, right padding */
.elementor-slideshow__header i {
	transform: translateX(-85px);
}
/* 1/6 display of gallery slider - this is to center it */
.elementor-slideshow__header .elementor-slideshow__counter {
	position: absolute;
}
/*__GALLERY_SLIDER__END__*/
```

## Archive
### ALLERGENE
A: Gluten - B: Krebstiere - C: Eier von Geflügel - D: Fisch - E: Erdnüsse - F: Sojabohnen - G: Milch von Säugetieren - H: Schalenfrüchte - L: Sellerie - M: Senf - N: Sesamsamen - O: Schwefeloxid und Sulfite - P: Lupinen - R: Weichtiere