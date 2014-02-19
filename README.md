cAdmin-Server
=============

  InterSystems Caché Administration Mobile tool - Server side. Bundled with project https://github.com/ShmidtIvan/cAdmin.
  
  Installation.
  1. Make Cachelib database read-write. (SMP → System Administration → Configuration → System Configuration → Local Databases, choose CACHELIB, uncheck Read Only, Save changes)
  2. Import all files into %SYS namespace.
  3. Compile classes.
  4. Make Cachelib database read-only (optional but recommended, see 1 for how-to).<br>
  
Notes.<br>
  If you import files into another database, make sure to mirror package SYS from CACHESYS database into this database.
  
