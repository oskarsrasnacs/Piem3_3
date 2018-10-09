# There are non-real and generated data in the spreadsheet files
# Autonumbering
# Oracle SQL Developer
# Imort .xlsx file
# Sequence
CREATE SEQUENCE S_Demogr_OR
START WITH 1
INCREMENT BY 1
CACHE 120;
# Trigger
create or replace TRIGGER TRIGGER_AUTONUM_DEMOGR_OR
BEFORE INSERT
ON DEMOGR_OR
REFERENCING NEW AS NEW
FOR EACH ROW
BEGIN
  if(:new.PatID is null) then
  SELECT S_DEMOGR_OR.nextval
  INTO :new.PatID
  FROM dual;
  end if;
END;
# PHP My Admin
# Import .ods file or with queries in the .xls file
CREATE TABLE Demogr_OR (
    PatID int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY,
    Place_of_residence int(1),
    Gender int(1),
Age int(3)	
    );
