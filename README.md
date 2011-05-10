sugar-spoonful (UNDER DEVELOPMENT)
====

Small rule based utility to tidy up files (like Mary Poppins singing 'A Spoonful of Sugar').

Installation
------------
(to do)


Usage
-----
Options:

      -x    Output only, does not execute any action on files.
      -l    Local mode, executes only the asked file and obviates .sugar files in target directories. 
      -s    Silent mode, does not output anything to screen.

It's ruby, so you can define variables

    shared_dir = 'home/rafa/shared'

Each directory to be checked is a source. You can declare as much as you want

    source '/home/rafa/downloads'
    source shared_dir

You define rules to apply to files. Rules defined at root level are applied globally to all sources.
If a file validates a rule, the file will be moved to the :target directory

    rule :pdfs, :extensions=>'pdf', :start_with=>'web', :target=>'/home/rafa/docs'
    rule :zips, :extensions=>'zip, rar, gz', :size_min=>'10M', :target=>'/home/rafa/tmp'

Besides extension and file name you will be able to check file date, size, etc.

You can define named rulesets, to be reused lately.

    ruleset 'videos' do
      rule :avi, :extensions=>'avi,mp4', :target=>'/home/rafa/tmp'
    end

You can create block sources where you can define your own sets of rules or import global rulesets.
By default block sources dont use the root(global) scope.

    source '/home/rafa/videos' do
      use_ruleset 'videos' #previous ruleset
    end

Local rule files
-----
You will be allowed to place a .sugar file in target directories with its own bunch of rules for subsequent rule matchings.




