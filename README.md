# utl-using-a-hex-dump-to-verify-the-layout-for-a-text-file
Using a hex dump to verify the layout for a text file
    Using a hex dump to verify the layout for a text file                                                              
                                                                                                                       
    There is a problem with the ops text file which should be fixed.                                                   
    The format should be corrected and resent.                                                                          
                                                                                                                       
    State is sometimes in field 4 and field 3?                                                                         
                                                                                                                       
    GitHub                                                                                                             
    https://tinyurl.com/y3qp87bo                                                                                       
    https://github.com/rogerjdeangelis/utl-using-a-hex-dump-to-verify-the-layout-for-a-text-file                       
                                                                                                                       
    macros                                                                                                             
    https://tinyurl.com/y9nfugth                                                                                       
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories                         
                                                                                                                       
    SAS Forum                                                                                                          
    https://tinyurl.com/yyxqw364                                                                                       
    https://communities.sas.com/t5/SAS-Programming/read-txt-file-with-appropriate-format-to-variables/m-p/693411       
                                                                                                                       
    The file fields should be separated by tabs, '09'x and in the following order                                      
                                                                                                                       
    d:/txt/President.txt                                                                                               
                                                                                                                       
        FullName                                                                                                       
        City                                                                                                           
        State                                                                                                          
        ASP                                                                                                            
        DOB                                                                                                            
        Term                                                                                                           
        Votes                                                                                                          
        PercVote                                                                                                       
                                                                                                                       
    Note ther third field should be state, however state appears to be in the fourth field                             
    on some records and the third field on others.                                                                     
                                                                                                                       
    Note the back to back tabs in 34 and 35.                                                                           
    This means State is missing in the third field and actualy apears in the fourt field.                              
                                                                                                                       
    CONSIDER RECORD 1 (State in field 4)                                                                               
                                                                                                                       
    George Washington  .  Pope's Creek     ..  Virginia.57.2/22/1732.1789                                              
    1...5....10...15.  .  .20...25...30..  .3  5...40...45...50...55...60                                              
    46676625676666766  0  567627247666222  00  56766666033032332333303333                                              
    75F275071389E74FE  9  0F057303255B000  99  69279E9195792F22F173291789                                              
                                                                                                                       
    CONSIDER RECORD 3 (State in field 3)                                                                               
                                                                                                                       
     --- Record Number ---  3   ---  Record Length ---- 63                                                             
                                                                                                                       
    Thomas Jefferson  .  Goochland County     .  Virginia.57.4/13/1742.1800                                            
    1...5....10...15  .  ..20...25...30...35  .  ..40...45...50...55...60..                                            
    5666672466667766  0  4666666662467677222  0  56766666033032332333303333                                            
    48FD130A566523FE  9  7FF38C1E403F5E49000  9  69279E9195794F13F174291800                                            
                                                                                                                       
    State shiuld not be in two different fields                                                                        
                                                                                                                       
    HEX DUMP (see GiHub Macros)                                                                                        
                                                                                                                       
    %utlrulr                                                                                                           
          (                                                                                                            
           uinflt =d:/txt/President.txt,                                                                               
           uprnlen =100,  /* Linesize for Dump */                                                                      
           ulrecl  =32760,  /* maximum record length */                                                                
           urecfm   =v,                                                                                                
           uobs = 3,        /* number of obs to dump */                                                                
           uchrtyp =ascii,  /* ascii or ebcdic */                                                                      
           uotflt =d:\txt\delete.txt                                                                                   
          );                                                                                                           
                                                                                                                       
                                                                                                                       
