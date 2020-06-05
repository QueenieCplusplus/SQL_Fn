# SQL_Fn
資料庫函數

    CREATE FUNCTION `fn_MemberCheck`(
    
      Level varchar(20)
      
    ) RETURNS int
    
        READS SQL DATA
        DETERMINISTIC
        
    BEGIN

      declare fn_level int;
      declare sql_result nvarchar(7000);
      set fn_level = Level;

      if fn_level = 0 then 

        set sql_result = 
 
          sql_statement_0;

      elseif fn_level = 1 then

        set sql_result = 
       
          sql_statement_1;

      elseif fn_level = 2 then

        set sql_result = 
  
            sql_statement_3; 

      end if;

      return sql_result; /* SQL function has return result.*/

    END
