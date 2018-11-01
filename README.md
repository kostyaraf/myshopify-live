# shopify-v1# myshopify-live

gulpfile.js:

////////////////////////////////////////////
// Gulp plugin setup
var gulp = require('gulp');
// Watches single files
var watch = require('gulp-watch');
var gulpShopify = require('gulp-shopify-upload');

gulp.task('shopifywatch', function() {
  return watch('./+(assets|layout|config|snippets|templates|locales)/**')
  .pipe(gulpShopify('4e84b5962c285fdb24ceabd8b6d8b8c8', '0c5d5dbb7a8fa3077fed99e5bb4806ab', 'kostyaraf.myshopify.com', '42320232507'))
  .pipe(browserSync.reload({
    stream: true
  }))
});

gulp.task('browserSync', function() {
    browserSync({
        server: {
            baseDir: 'app'
        }
    })
})

// Default gulp action when gulp is run
gulp.task('default', [
  'shopifywatch'
]);
////////////////////////////////////////////

// Syntaxis:
.pipe(gulpShopify('API', 'PASS-FOR-API', 'SHOP-NAME.myshopify.com', 'ID-THEME-OPTIONAL'))
