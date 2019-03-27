## MySQL_Trigger



#### Today I learn



##### Trigger is activated when MySQL runs INSERT, UPDATE, DELETE statement

```mysql
CREATE TABLE deletedUserTBL (
    userID char(8),
    userName char(5),
    userMobile char(20),
    deletedDate date -- date when it is got rid of 
);

DELIMITER //
CREATE TRIGGER trigger_deletedUserTBL -- the name of trigger
	AFTER DELETE -- activated after data has been deleted
	ON UserTBL
	FOR EACH ROW -- apply this to each row
BEGIN
	-- Data from old(o) table is inserted
	INSERT INTO deletedUserTBL
		VALUES (O.userID, O.userName, O.userMobile, CURDATE() );
END //

DELIMITER ;
```

