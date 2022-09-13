# Zeno Filesystem

Zeno is the distributed filesystem that powers Pleroma.  It is where all (most) system and user files are stored.

Two entity types power Zeno: `ZenoMaster` and `ZenoNode`.

Each node with a `storage` resource runs a ZenoNode entity, and a cluster-wide `ZenoMaster` entity runs on any regular node.

All files are stored as chunks spread across ZenoNodes, which are indexed by the ZenoMaster node.  The chunk size is tunable, but is set to a sane default.

Each chunk is replicated across 3 nodes (or however many `stable` nodes your system has).

## Telescoping Tag System

The primary difference in usability between a typical filesystem and Zeno, is that Zeno uses tags rather than paths.

On a typical filesystem, you might have a path called `System > Programs > ...` which lists all directories of every program.

In Zeno, files have a name, but directories don't exist.  Instead, every file has multiple tags, e.g.

`
filename: MyPhoto.jpg
user: MyUser
who: Will
type: FamilyPhotos
`

and you can view these tags through a "telescope" or "lens".  The lens allows you to change the structure of your files without affecting the underlying files.

Here's one example:

Let's say you wanted to see all your personal photos that contain you, and all your personal photos that contain Bob.  You could create two directories, one called "Me" and another called "Bob", and copy and paste the photos into each directory.  There would be some duplication, as you and Bob are coworkers and appear in several photos together.

Alternatively, we could just add a tag `in-photo: Bob` or `in-photo: Will` to each photo (or you add both tags).  Now we can easily use a lens to achieve what we wanted:

`Photos > Bob:(in-photo:Bob), Me:(in-photo:Me), Together:(in-photo:Bob + in-photo:Me)`

When viewed through this lens, you'll see a directory `Photos` that contains three other directories `Me`, `Bob`, and `Together`.  All photos tagged with `in-photo: Bob` will be placed in the Bob directory, etc.  No file duplication required.

By default, Pleroma provides a system lens, and a user lens that mimics what one might expect from a classic operating system.

## Usage

`~zeno`

`checkout(path: str, lens: Lens) -> Zfile` - checks out and locks the current file.  It calls ZenoMaster, finds the location of the associated file chunks, assembles them by contacting each ZenoNode entity, and then returns the file.  You can specify what type of lock-access is required: multiple-reader, multiple-reader-single-writer, or exclusive.

`look(lens: Lens)` - Takes a lens pattern and returns the associated file view.

## Capabilities

Programs are namespaced to their own tag (with the right capabilities).  Programs naturally cannot see anything outside of their own tag, unless they specifically request it via another capability.

# Local Filesystem

Local filesystems can still be accessed as normal using `~fs`, but it is discouraged unless absolutely necessary.
