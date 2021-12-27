# section-s
lude-once #include &lt;File.au3> #include &lt;array.au3> ;Test function to write comments to an ini file Global $IniFile = @ScriptDir &amp; "\Test.ini" FileOpen($IniFile, 2) IniWrite($IniFile, "Test1", 1, 1) IniWrite($IniFile, "Test1", 2, 2) IniWrite($IniFile, "Test1", 3, 3) IniWrite($IniFile, "Test1", 4, 4) IniWrite($IniFile, "Test2", 1, 1) IniWrite($IniFile, "Test2", 2, 2) IniWrite($IniFile, "Test2", 3, 3) IniWrite($IniFile, "Test3", 1, 1) IniWrite($IniFile, "Test3", 2, 2) IniWrite($IniFile, "Test3", 3, 3) Global $Test = _IniWriteSectionComment($IniFile, "Test1", "This is a comment that comes before a section name", 1) $Test = _IniWriteSectionComment($IniFile, "Test2", "This is a comment that comes after a section name", 0) $Test = _IniWriteSectionComment($IniFile, "Test3", "This is a multi-line comment|that comes after a section name", 0) $Test = _IniWriteSectionComment($IniFile, "Test4", "This will cause an error by referencing a non-existent section name", 0) ConsoleWrite('@@ Debug(' &amp; @ScriptLineNumber &amp; ') : $Test = ' &amp; $Test &amp; @crlf &amp; '>Error code: ' &amp; @error &amp; @crlf) ;### Debug Console $Test = _IniWriteSectionComment($IniFile, "Test3", "This is a NEW multi-line comment|that comes after a section name", 0) $Test = _IniWriteSectionComment($IniFile, "Test3", "This is a multi-line comment|that comes before a section name", 1) ;~ $Test = _IniStripComments($IniFile, 0, "Test3", 1) ; This will strip the comments from before the section Test3 ; #FUNCTION# ==================================================================================================================== ; Name...........: _IniWriteSectionComment ; Description ...: Writes comment(s) to an .ini file ; Syntax.........: _IniWriteSectionComment($IWSC_FileName, $IWSC_SectionName, $IWSC_Comment[, $IWSC_ForeAft = 1]) ; Parameters ....: $IWSC_FileName      - String path of the file to write to. ;                 $IWSC_SectionName    - The section of the ini file to comment. ;                 $IWSC_Comment     - String that contains the comment for the section name. ;                 $IWSC_ForeAft     - Optional: Specifies where to put the comment in relation to the section name ;                                        default is before the section name. ; Return values .: Success - Returns a 1 ;                 Failure - Returns a 0
