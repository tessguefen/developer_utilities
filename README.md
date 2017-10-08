# Devkit

## All Functions
```xml
<mvt:item name="devkit" param="Format_Currency( price, formatted_price var )" />
<mvt:item name="devkit" param="Upcharge( charge_name, charge_type, amount, tax_exempt )" />
<mvt:item name="devkit" param="Variant_Array( product_id, variants var )" />
<mvt:item name="devkit" param="Date( format, timestamp, return var )" />
<mvt:item name="devkit" param="Load_Product( options var, product var )" />
<mvt:item name="devkit" param="Product_Load_Imagetype( product_id, type_code, image_width, image_height, output var )" />
<mvt:item name="devkit" param="ProductArray_Load_Imagetype( product_array var, type_code, image_width, image_height, member )" />
<mvt:item name="devkit" param="SQL( parameters var )" />
<mvt:item name="devkit" param="Category_Product_Image( category_id, type_code, image_width, image_height, output var )" />
<mvt:item name="devkit" param="JSON_Output_Variable( value var, output var )" />
<mvt:item name="devkit" param="JSON_Output_Floats_Variable( value var, output var )" />
<mvt:item name="devkit" param="Next_Weekday( timestamp, dow, output var )" />
<mvt:item name="devkit" param="Page_Render_Variable( page_code, output var )" />
<mvt:item name="devkit" param="Recently_Viewed_Products( customfield_name, max, current_product_code, type_code, image_width, image_height, image_member, output var )" />
<mvt:item name="devkit" param="ShippingMethodList_ForItems( basket var, items var, output var )" />
<mvt:item name="devkit" param="Category_Tree_Image( category_id, output var )" />
<mvt:item name="devkit" param="Category_Title_Image( category_id, output var )" />
<mvt:item name="devkit" param="Scheduled_Promo_PriceGroup( pricegroup_name, output var )" />
<mvt:item name="devkit" param="Readytheme_Load_ContentSection_NoDiv_Variable( code, all_settings var, output var )" />
<mvt:item name="devkit" param="Readytheme_Load_ContentSection_NoDiv( code, all_settings var )" />
<mvt:item name="devkit" param="Free_Shipping_Qualifying( threshold, basket_total, output var )" />
<mvt:item name="devkit" param="Group_By_Member( array var, member, results var )" />
<mvt:item name="devkit" param="Hidden_Fields( fields )" />
<mvt:item name="devkit" param="Send_Email_Attachment_Custom( from, to, cc, subject, body_message, file_name, file_dir, file_location, result var )" />
<mvt:item name="devkit" param="Products_Also_Purchased_Query( product_id, max, type_code, image_width, image_height, image_member, output var )" />
<mvt:item name="devkit" param="ItemGroup_Group_Items( items var, custom_attribute, regular_items var, grouped_items var )" />
<mvt:item name="devkit" param="Create_Customer_Email_Password( email, password, password_confirm, messages var, redirect_to )" />
<mvt:item name="devkit" param="ReOrder_Order_Form( orderitems var, show_quantity_inputs, member )" />
<mvt:item name="devkit" param="Replace_Special_Characters( input_string, outputstring var )" />
<mvt:item name="devkit" param="Product_Images_Srcset( product_id, type_code, image_width, image_height, output var )" />
<mvt:item name="devkit" param="Assign_Member( variable var, member, value )" />
<mvt:item name="devkit" param="Assign_Index( array var, index, value )" />
<mvt:item name="devkit" param="Parse_URI( uri, return var )" />
<mvt:item name="devkit" param="URI_QueryStrings_To_Structure( uri, array, return var )" />
<mvt:item name="devkit" param="URI_Add_Replace_QueryString( uri, query_string, value, return var )" />
<mvt:item name="devkit" param="URI_Build_URI( uri var, output var )" />
<mvt:item name="devkit" param="URI_Add_Replace_Subdomain( uri, new_subdomain, output var )" />
<mvt:item name="devkit" param="URI_Add_Replace_UserPass( uri, user, pass, output var )" />
<mvt:item name="devkit" param="URI_Add_Replace_Scheme( uri, new_scheme, output var )" />
<mvt:item name="devkit" param="URI_Replace_TLD( uri, new_tld, output var )" />
<mvt:item name="devkit" param="URI_Replace_Hash( uri, new_hash, output var )" />
<mvt:item name="devkit" param="Minify_CSS( css_string, output var )" />
<mvt:item name="devkit" param="Minify_CSS_File( source_path, dest_path, check_modified )" />
<mvt:item name="devkit" param="Minify_Concat_CSS_Files( source_paths, dest_path, check_modified )" />
<mvt:item name="devkit" param="Minify_JS( js_string, output var )" />
<mvt:item name="devkit" param="Minify_JS_File( source_path, dest_path, check_modified )" />
```

## Load_Product

```xml
<h2>Component</h2>

<mvt:assign name="g.options:code" value="'apple'" />
<mvt:item name="developer_util" param="Load_Product(g.options, g.product_foo)" />
<hr>
<mvt:eval expr="glosub(miva_array_serialize(g.product_foo), ',', '<br>')" />


<h2>mvt:do</h2>
<mvt:assign name="l.options:code" value="'apple'" />
<mvt:assign name="l.options:include" value="'runtime,currency,uris,url'" />
	<mvt:assign name="g.Module_Developer_Utitlities" value="g.Module_Root $ 'modules/util/developer_util.mvc'" /><mvt:comment><!-- Find way for module path global variable to be available to page by default --></mvt:comment>
<mvt:do file="g.Module_Developer_Utitlities" name="l.product_v2" value="_Load_Product(l.options)" />
<hr>
<mvt:eval expr="glosub(miva_array_serialize(l.product_v2), ',', '<br>')" />
```

## SQL
```xml
<mvt:assign name="l.settings:parameters:query" value="'SELECT * FROM ' $ g.Store_Table_Prefix $ 'Products WHERE id = ?'" />
<mvt:assign name="l.success" value="miva_array_insert( l.settings:parameters:bind_parameters, '290', -1 )" />
<mvt:item name="dev_util" param="SQL( l.settings:parameters )" />
<mvt:eval expr="glosub(miva_array_serialize(l.settings:parameters:results ), ',', '<br />')" />
```

## Helper Variables

### Timespans

| Variable | Value |
|----------|-------|
| g.DK_MINUTE_IN_SECONDS | 60 |
| g.DK_HOUR_IN_SECONDS | 3600 |
| g.DK_DAY_IN_SECONDS | 86400 |
| g.DK_WEEK_IN_SECONDS | 604800 |
| g.DK_MONTH_IN_SECONDS | 2592000 |
| g.DK_YEAR_IN_SECONDS | 31536000 |

### Filesizes
| Variable | Value |
|----------|-------|
| g.DK_KB_IN_BYTES | 1024 |
| g.DK_MB_IN_BYTES | 1048576 |
| g.DK_GB_IN_BYTES | 1073741824 |
| g.DK_TB_IN_BYTES | 1099511627776 |


## Minify CSS & JS

```xml
<h2>mvt:do Do_File_Write</h2>
<mvt:do file="g.Module_Devkit" name="l.settings:result" value="Do_File_Write( '/foobar.txt', 'script', 'Hello World', 0 )" />

<h2>DevKit File_Write</h2>
<mvt:item name="devkit" param="File_Write( '/foobar-2.txt', 'script', '|Check this out', 0, l.result )" />

<h2>mvt:do Do_Concat_Files</h2>
<mvt:assign name="l.files[1]" value="'/foobar.txt'" />
<mvt:assign name="l.files[2]" value="'/foobar-2.txt'" />
<mvt:do file="g.Module_Devkit" name="l.settings:result" value="Do_Concat_Files( l.files )" />
result=&mvt:result;

<h2>mvt:do Do_Concat_Files</h2>
<mvt:assign name="l.settings:files[1]" value="'/foobar.txt'" />
<mvt:assign name="l.settings:files[2]" value="'/foobar-2.txt'" />
<mvt:item name="devkit" param="Concat_Files( l.settings:files, l.settings:result )" />
result=&mvt:result;

<h2>mvt:do Do_Minify_CSS</h2>
<mvt:assign name="l.result" value="file_read( '/mm5/themes/booc/js/jquery.min.js', 'script' , l.expanded_css )" />
<mvt:do file="g.Module_Devkit" name="l.minified_css" value="Do_Minify_CSS( l.expanded_css )" />
<mvt:eval expr="l.minified_css" />

<h2>DevKit Minify_CSS</h2>
<mvt:assign name="l.result" value="file_read( '/mm5/css/00000001/cssui.css', 'script' , l.settings:expanded_css )" />
<mvt:item name="devkit" param="Minify_CSS( l.settings:expanded_css, l.settings:minified_css )" />
&mvt:minified_css;

<h2>mvt:do Do_Minify_JS</h2>
<mvt:assign name="l.result" value="file_read( '/js/mvscreen.js', 'script' , l.expanded_js )" />
<mvt:do file="g.Module_Devkit" name="l.minified_js" value="Do_Minify_JS( l.expanded_js )" />
<mvt:eval expr="l.minified_js" />

<h2>DevKit Minify_JS</h2>
<mvt:assign name="l.result" value="file_read( '/js/mvscreen.js', 'script' , l.settings:expanded_js )" />
<mvt:item name="devkit" param="Minify_JS( l.settings:expanded_js, l.settings:minified_js )" />
&mvt:minified_js;

<h2>mvt:do Do_Minify_CSS_File</h2>
<mvt:do file="g.Module_Devkit" name="l.settings:result" value="Do_Minify_CSS_File( '/mm5/css/00000001/cssui.css', '/mm5/css/00000001/cssui.min.css', 1 )" />
result=&mvt:result;

<h2>DevKit Minify_CSS_File</h2>
<mvt:item name="devkit" param="Minify_CSS_File( '/mm5/css/00000001/cssui.css', '/mm5/css/00000001/cssui.min.css', 1 )" />

<h2>mvt:do Do_Minify_JS_File</h2>
<mvt:do file="g.Module_Devkit" name="l.settings:result" value="Do_Minify_JS_File( '/js/mvscreen.js', '/js/mvscreen.min.js', 1 )" />
result=&mvt:result;

<h2>DevKit Minify_JS_File</h2>
<mvt:item name="devkit" param="Minify_JS_File( '/js/mvscreen.js', '/js/mvscreen.min.js', 1 )" />

<h2>mvt:do Do_Minify_Concat_CSS_Files</h2>
<mvt:assign name="l.css_files[1]" value="'/mm5/css/00000001/cssui.css'" />
<mvt:assign name="l.css_files[2]" value="'/mm5/css/00000001/minibasket.css'" />
<mvt:assign name="l.css_files[3]" value="'/mm5/css/00000001/readytheme.css'" />
<mvt:do file="g.Module_Devkit" name="l.settings:result" value="Do_Minify_Concat_CSS_Files( l.css_files, '/mm5/css/00000001/all.min.css', 1 )" />

<h2>devkit Minify_Concat_CSS_Files</h2>
<mvt:assign name="l.settings:css_files[1]" value="'/mm5/css/00000001/cssui.css'" />
<mvt:assign name="l.settings:css_files[2]" value="'/mm5/css/00000001/minibasket.css'" />
<mvt:assign name="l.settings:css_files[3]" value="'/mm5/css/00000001/readytheme.css'" />
<mvt:item name="devkit" param="Minify_Concat_CSS_Files( l.settings:css_files, '/mm5/css/00000001/all.min.css', 0 )" />

<h2>mvt:do Do_Minify_Concat_JS_Files</h2>
<mvt:assign name="l.js_files[1]" value="'/mm5/themes/booc/js/jquery.min.js'" />
<mvt:assign name="l.js_files[2]" value="'/mm5/themes/booc/js/plugins.js'" />
<mvt:comment><mvt:assign name="l.js_files[3]" value="'/mm5/themes/booc/js/scripts.js'" /></mvt:comment>
<mvt:do file="g.Module_Devkit" name="l.settings:result" value="Do_Minify_Concat_JS_Files( l.js_files, '/mm5/themes/booc/js/all.min.js', 0 )" />

<h2>devkit Minify_Concat_JS_Files</h2>
<mvt:assign name="l.settings:js_files[1]" value="'/mm5/themes/booc/js/jquery.min.js'" />
<mvt:assign name="l.settings:js_files[2]" value="'/mm5/themes/booc/js/plugins.js'" />
<mvt:comment><mvt:assign name="l.settings:js_files[3]" value="'/mm5/themes/booc/js/scripts.js'" /></mvt:comment>
<mvt:item name="devkit" param="Minify_Concat_JS_Files( l.settings:js_files, '/mm5/themes/booc/js/all.min.js', 1 )" />

<!--
TODO: Do_Site_CSS - Pass in array of css file paths, minify them, and output a single <link> tag for the minified & concatinated file (with ?v=1234 timestamp cache-buster). For debugging/development, pass g.DK_Expand OR g.DK_Expand_CSS to output each source-file <link> tag instead of minifed css file.
TODO: Do_Site_JS - Pass in array of js file paths, minify them, and output a single <script> tag for the minified & concatinated file (with ?v=1234 timestamp cache-buster). For debugging/development, pass g.DK_Expand OR g.DK_Expand_JS to output each source-file <script> tag instead of minifed js file.
-->
```