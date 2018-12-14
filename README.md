# utl-alter-the-lengths-of-all-charater-variables-at-once
Alter the lengths of all charater variables at once 
    Alter the lengths of all charater variables at once                                                               
                                                                                                                      
    gitub                                                                                                             
    https://tinyurl.com/y7dygn9m                                                                                      
    https://github.com/rogerjdeangelis/utl-alter-the-lengths-of-all-charater-variables-at-once                        
                                                                                                                      
    SAS Forum                                                                                                         
    https://tinyurl.com/y8gpgmlf                                                                                      
    https://communities.sas.com/t5/New-SAS-User/More-efficient-way-to-truncate-many-variables-at-once/m-p/521202      
                                                                                                                      
                                                                                                                      
    INPUT                                                                                                             
    =====                                                                                                             
                                                                                                                      
     WORK.HAVE total obs=3                                                                                            
                                                                                                                      
         DX1         DX2       DX3     DX4      DX5         DX6         DX7                                           
                                                                                                                      
       F15.151X    S32.602                                S72.401B    T79.4XX                                         
       W34.00XA    R57.0BB    N28.9                                                                                   
       S81.801A    K21.9FF    E87.6           S71.132A                                                                
                                                                                                                      
                                                                                                                      
    EXAMPLE OUTPUT                                                                                                    
    --------------                                                                                                    
                                                                                                                      
    WORK.WANT total obs=3                                                                                             
                                                                                                                      
           Length 3                       Original variables                                                          
       ------------------------          -----------------------------                                                
       DX1    DX2    DX3    DX7  ...      OX1         OX2   ...    OX7                                                
                                                                                                                      
       F15    S32           T79  ...    F15.151X    S32.602 ...  T79.4XX                                              
       W34    R57    N28         ...    W34.00XA    R57.0BB ...                                                       
       S81    K21    E87         ...    S81.801A    K21.9FF ...                                                       
                                                                                                                      
                                                                                                                      
    PROCESS                                                                                                           
    =======                                                                                                           
                                                                                                                      
    data want;                                                                                                        
     length dx1-dx7 $3;                                                                                               
     merge have have(rename=(dx1-dx7=ox1-ox7));                                                                       
    run;quit;                                                                                                         
                                                                                                                      
                                                                                                                      
    OUTPUT                                                                                                            
    ======                                                                                                            
                                                                                                                      
    see above                                                                                                         
                                                                                                                      
    *                _              _       _                                                                         
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _                                                                  
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |                                                                 
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |                                                                 
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|                                                                 
                                                                                                                      
    ;                                                                                                                 
                                                                                                                      
    data have;                                                                                                        
     input (DX1 DX2 DX3 DX4 DX5 DX6 DX7) ($) ;                                                                        
    cards4;                                                                                                           
    F15.151X S32.602 . . .                                                                                            
    S72.401B T79.4XX R78.81 G82.20 S22.39XA J96.90 M79.5                                                              
    W34.00XA R57.0BB N28.9 . . . .                                                                                    
    S81.801A K21.9FF E87.6 . S71.132A . .                                                                             
    ;;;;                                                                                                              
    run;quit;                                                                                                         
                                                                                                                      
                                                                                                                      
                                                                                                                      
                                                                                                                      
                                                                                                                      
                                                                                                                      
                                                                                                                      
                                                                                                                      

