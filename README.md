Collection of vim and related stuff, mostly simple, but still good to
keep them in the back of your head.


#### Rename a ruby gem - and therefore namespaces across all files

Renamed llt-diff to llt-review
- going to top folder of the gem
- `vim **/*.rb` loads all files to the argument list
- `:argdo %s/Diff\(erence\)\@!/Review/e | update
  - Replace Diff with Review in all files, unless the word is Difference
  - No `g` flag, because we have `gdefault` set
  - `e` flag ignores errors when a file has no match (such as
    `spec_helper.rb`
  - `update` saves all files immediately after the substitution
- `:argdo %s/\(require.\+\)\@<=diff\(erence\)\@!/review/e | update`
  - replace all diff in a line that has a require to review
- don't forget to upadte `config.ru`, `gemspec` and `Readme`
