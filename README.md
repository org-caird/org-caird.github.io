# GitHub Pages for Organization for Clinical AI Research and Development

## How to build the site by Bundler

1. Change current directory to the document root.

   ```
   cd docs
   ```
2. Designate a subdirectory `vendor` to the ruby platform that `bundler` provides.
   ```
   bundler config set path vendor; bundle config set --local force_ruby_platform true
   ```
3. Install the ruby platform and relevant gems into the target location.
   ```
   bundler install
   ```
4. Call Jekyll to build and serve the preview.
   ```
   bundler exec jekyll serve -o
   ```
5. Optionally, remove the cache if you would like to rebuild the generated files from scratch.
   ```
   bundler exec jekyll clean
   rm -rf vendor/ .bundle/ Gemfile.lock
   ```

## How to build the site via Nix

1. Change current directory to the document root.

   ```
   cd docs
   ```
2. Designate a subdirectory `vendor` to the ruby platform that `bundler` provides.
   ```
   nix-shell -p bundler --run "bundler config set path vendor; bundle config set --local force_ruby_platform true"
   ```
3. Install the ruby platform and relevant gems into the target location.
   ```
   nix-shell -p bundler --run "bundler install"
   ```
4. Call Jekyll to build and serve the preview.
   ```
   nix-shell -p bundler --run "bundler exec jekyll serve -o"
   ```
5. Optionally, remove the cache if you would like to rebuild the generated files from scratch.
   ```
   nix-shell -p bundler --run "bundler exec jekyll clean"
   rm -rf vendor/ .bundle/ Gemfile.lock
   ```
