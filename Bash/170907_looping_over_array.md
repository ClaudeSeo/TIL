### Today I learned how to create and loop over bash arrays in the process of creating a custom scss -> css -> min.css script

```bash
#!/bin/bash

# GENERAL NOTES
# node-sass must be globally installed for this to work
# if it is not, run `npm install -g node-sass`
# clean-css-cli must be globally installed for this to work
# if it is not, run `npm install clean-css-cli -g`

# declare some file paths we will use often
css_path="./www/css/"
# compile all scss into css
eval "node-sass $css_path -o $css_path"
# minify all css into min.css
css_array=("home" "ionic.segment" "media-queries" "secondary-media-queries" "style")
for i in "${css_array[@]}"
do
  eval "cleancss -o $css_path/$i.min.css $css_path/$i.css"
done
```
