# SQL_Fn
資料庫函數

* IPC

call fun in usp

https://www.mysqltutorial.org/mysql-stored-function/

* Script

    DELIMITER $$

    CREATE PROCEDURE GetCustomerLevel(
        IN  customerNo INT,  
        OUT customerLevel VARCHAR(20)
    )
    BEGIN

        DECLARE credit DEC(10,2) DEFAULT 0;

        -- get credit limit of a customer
        SELECT 
            creditLimit 
        INTO credit
        FROM customers
        WHERE 
            customerNumber = customerNo;

        -- call the function 
        SET customerLevel = CustomerLevel(credit);
    END$$

    DELIMITER ;



* Template



        sys.fn_get_sql ( SqlHandle )  


        DECLARE @Handle varbinary(64);  
        SELECT @Handle = sql_handle   
        FROM sys.dm_exec_requests   
        WHERE session_id = 52 and request_id = 0;  
        SELECT * FROM sys.fn_get_sql(@Handle);  
        GO  


    SQL Script

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
