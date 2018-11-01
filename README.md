# shopify-v1# myshopify-live
<br>
<b>gulpfile.js:</b><br>
<br>
////////////////////////////////////////////<br>
// Gulp plugin setup<br>
var gulp = require('gulp');<br>
// Watches single files<br>
var watch = require('gulp-watch');<br>
var gulpShopify = require('gulp-shopify-upload');<br>
<br>
gulp.task('shopifywatch', function() {<br>
&nbsp;&nbsp;&nbsp;&nbsp; return watch('./+(assets|layout|config|snippets|templates|locales)/**')<br>
&nbsp;&nbsp;&nbsp;&nbsp; .pipe(gulpShopify('4e84b5962c285fdb24ceabd8b6d8b8c8', '0c5d5dbb7a8fa3077fed99e5bb4806ab', 'kostyaraf.myshopify.com', '42320232507'))<br>
&nbsp;&nbsp;&nbsp;&nbsp; .pipe(browserSync.reload({<br>
&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; stream: true<br>
&nbsp;&nbsp;&nbsp;&nbsp; }))<br>
});<br>
<br>
gulp.task('browserSync', function() {<br>
&nbsp;&nbsp;&nbsp;&nbsp; browserSync({<br>
&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; server: {<br>
&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; baseDir: 'app'<br>
&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; }<br>
&nbsp;&nbsp;&nbsp;&nbsp; })<br>
})<br>
<br>
// Default gulp action when gulp is run<br>
gulp.task('default', [<br>
&nbsp;&nbsp;&nbsp;&nbsp; 'shopifywatch'<br>
]);<br>
////////////////////////////////////////////<br>
<br>
<b>// Syntaxis:</b><br>
.pipe(gulpShopify('API', 'PASS-FOR-API', 'SHOP-NAME.myshopify.com', 'ID-THEME-OPTIONAL'))<br>
