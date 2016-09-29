# Guardfile

## Uncomment and set this to only include directories you want to watch
# directories %w(app lib config test spec features) \
#  .select{|d| Dir.exists?(d) ? d : UI.warning("Directory #{d} does not exist")}

## Note: if you are using the `directories` clause above and you are not
## watching the project directory ('.'), then you will want to move
## the Guardfile to a watched dir and symlink it back, e.g.
#
#  $ mkdir config
#  $ mv Guardfile config/
#  $ ln -s config/Guardfile .
#
# and, you'll have to watch "config/Guardfile" instead of "Guardfile"

guard 'nanoc' do
  watch /^nanoc.yaml/
  watch /^Rules/
  watch %r{^(content|layouts|lib)/.*$}
end

guard 'livereload' do
  # remember you need either the script or the browser extension
  watch %r{^output/.*$}
end

guard :bundler do
  watch('Gemfile')
end
