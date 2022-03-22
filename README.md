# Pass-File
Khóa thư mục 

Copy đoạn code
```
 cls
 @ECHO OFF
 title My Folder
 if EXIST "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" goto UNLOCK
 if NOT EXIST DauDau goto MDLOCKER
 :CONFIRM
 echo Ban co chac chan muon khoa thu muc DauDau khong? (Y = Co / N = Khong)
 set/p "cho=>"
 if %cho%==Y goto LOCK
 if %cho%==y goto LOCK
 if %cho%==N goto END
 if %cho%==k goto END
 echo Invalid choice.
 goto CONFIRM
 :LOCK
 ren DauDau "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
 attrib +h +s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
 echo Folder locked
 goto End
 :UNLOCK
 echo Hay nhap mat khau de mo khoa:
 set/p "pass=>"
 if NOT %pass%== pass của bạn goto FAIL
 attrib -h -s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
 ren "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" DauDau
 echo Folder Unlocked successfully
 goto End
 :FAIL
 echo Invalid password
 goto end
 :MDLOCKER
 md DauDau
 echo DauDau created successfully
 goto End
 :End
```
