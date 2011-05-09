sugar-spoonful
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
      -s    Silent mode, does not output anything to screen

    #it's ruby, so you can define variables
    shared_dir = 'home/rafa/shared'

    #each directory to be checked is a source
    #you can declare as much as you want
    source '/home/rafa/downloads'
    source shared_dir

    #you define rules to apply to files
    #rules defined at root level are applied globally to all sources
    #if a file validates a rule, the file will be moved to the :target directory
    rule :pdfs, :extensions=>'pdf', :target=>'/home/rafa/docs'

    #you can define rulesets, to be reused lately
    ruleset 'videos' do
      rule :avi, :extensions=>'avi,mp4', :target=>'/home/rafa/tmp'
    end

    #you can create block sources where you can define your own sets of rules 
    #or import global rulesets
    #by default block sources dont use the root(global) scope
    source '/home/rafa/videos' do
      use_ruleset 'videos' #previous ruleset
    end

    #local rule files
    #you will be allowed to place a .sugar file in target directories 
    #with its own bunch of rules for subsequent rule matchings




