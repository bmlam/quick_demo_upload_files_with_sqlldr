# quick_demo_upload_files_with_sqlldr

To create the target table:

create table TEST_CLOB (
 id number
 , file_name varchar2(100)
 , text clob
); 

Only 3 files are needed for this demo:

load_cfg.txt. is the control file (the file extension being chosen arbitrarily) 
test_clob.csv:  maps the target table columns to file paths on the sqlldr client. The csv is referenced by the control file
some_shell_script: is an examplary payload file to be uploaded

Fire up the upload with:

$ sqlldr userid=test/test@db10g control=loader_cfg.txt log=load_lob.log bad=load_lob.bad

