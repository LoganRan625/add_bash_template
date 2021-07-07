# Contents
  1. mksh
  2. add_bash_templates
  3. BEFORE RUNNING
  4. WHAT DOES add_bash_templates DO\?
  5. USAGE

# mksh
running mksh will create a file, name, give permissions and add header 
(name, date, type, time, copyright, ...) mksh will execute 
add_bash_templates, which will grep all template headers to give you a menu
so you can add the templates you wish to use.

the value of this is you can quickly add code templates you are 
aware you will need, like "for loops", "main function", "nested if statements, nested for loops, nested functions"
then fill the templates with your code. it simply speeds up the process of organizing
and writing bash files, also by filling the header with nessesary 
info for you, automating the process, saving you time.

  EXAMPLE FILE:
  
    #!/usr/bin/env bash

        ################################################
        # Name: new_sh_file          Date: 07/06/21
        # Time: 01:22                Type: Bash
        # Copyright: none
        # Goal:
        #
        ################################################

    # section_variables

    ########## header files ###########
    #source ./<path/somefilename>
    #source ./<path/somefilename> 

    ########### variables #############
    a1=$1; a2=$2; a3=$3; a4=$4

    #_ section_functions

    ########### functions #############

    #_ missing_requirements_exit
    
    # error function 
    function error(){
         echo "[$(date +'%Y-%m-%dT%H:%M:%S%z')]: $*" >&2
    }

    # didnt supply any arguments when executing script
    if [[ $# -lt 0 ]]; then
        err "Missing required argument\n"
        exit 1
    fi

    # did not run as root
    if [[ $UID == 1 ]];then 
        err "Error: you must be root to run this script, try sudo <scriptname>"
        exit 1
    fi

    #_ section_main

    ############# main ################


    #_ skeleton_main_while_if
    function main(){ # <arg1> <arg2>
        local input1
        local input2
        input1=$1
        input2=$2
        # infinite loop
        while :
        do
                if [[ $1 == 1 ]]; then
                        #something
                elif [[ $2 < 1 ]]; then
                        #something
                else
                        #something
                fi
        done
    }


# add_bash_templates

choose templates of functions, variables, loops, etc... from a bash_templates file to add to your file.sh
whats great about this is the entire process is sizable. you can remeove any templates or add any custom 
templates to **"bash_templates"** file. as long as you follow the "Example:" under **"BEFORE RUNNING:"**
if the template header in the file does not have the proper syntax it may not get picked up as an option 
in the **"add_bash_templates"** menu.

# BEFORE RUNNING:

For this to work you need
  1) add_bash_templates
  2) bash_templates 
  3) mksh

add your own custom templates inside \<bash_templates\>
  
Before and after each template in \<bash_templates\> 
  1) line must start with "#_ " on the same line
  2) the title of the template seperated by "_"
    
   EXAMPLE "#_ basic_functions"
   
      note
      
      without an underscore in the name it will
      not show in list of avialable templates to choose


# WHAT DOES add_bash_templates DO\?:
  
  creates a list of templates to choose from by number, the
  selected template is then found in the file \<bash_templates\>
  and added to your new bash file \<tmp.sh\>. 


# USAGE: 

MAKING A NEW .sh FILE
  
   Syntax
   
     ./mksh


ADDING TO EXISTING FILE

   Syntax 
   
     ./add_bash_template <arg1> 

   Example 
        
     ./add_bash_template file.sh
  

