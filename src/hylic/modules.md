# Hylic - Modules

Every file exists in a module, and modules are imported by path.

At the top of the file, you define your module `foo`.  No matter what, that module can always be accessed in all other files as `~foo`.  If you have multiple files with `foo`, then you can imagine all of them are concatenated together (no ordering).  Directory structure is ignored and replaced by whatever you specify.

## Dependencies

TBD
