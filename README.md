# add_bash_template
choose which functions, variables, common loops, from a template file to add to your filename.sh


# BEFORE RUNNING:

For this to work you need both
  1) add_bash_templates
  2) bash_templates 
  3) mksh

add your own templates inside \<bash_templates\>
  
Before and after each template in \<bash_templates\> 
  1) line must start with "#_ " on the same line
  2) the title of the template seperated by "_"
    
   EXAMPLE "#_ basic_functions"
   
      note; without an underscore in the name it will
      not show in list of avialable templates to choose


# WHAT IT DOES:
  
  creates a list of templates to choose from by number, the
  selected template is then found in the file \<bash_templates\>
  and added to your new bash file \<tmp.sh\>. 


# USAGE: 

MAKING A NEW  \?.sh FILE

  
   Syntax
   
     mksh


ADDING TO EXISTING FILE


   Syntax 
   
     ./add_bash_template <arg1> 

   Example 
        
     ./add_bash_template file.sh
  

