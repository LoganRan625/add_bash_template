# add_bash_template
choose which functions, variables, common loops, from a template file to add to your filename.sh


BEFORE RUNNING:

For this to work you need both
  1) add_bash_template file
  2) bash_templates file
  
Before and after each template in <bash_templates> 
  1) line must start with "#_ " on the same line
  2) the title of the template seperated by "_"
   EXAMPLE "#_ basic_functions"
     # without an underscore in the name it will
     # not show in list of avialable templates to choose


WHAT IT DOES:
  
  creates a list of templates to choose from by number, the
  selected template is then found in the file <bash_templates>
  and added to your new bash file <tmp.sh>. 


USAGE: 

  Syntax "./add_bash_template <arg1>"

  Example "./add_bash_template newfile.sh"
  

