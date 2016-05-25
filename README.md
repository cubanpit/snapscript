# snapscript

Script to simplify btrfs snapshots management.

Use it at your own risk, there is no guarantee that this scripts does not kill you system.

This script require `btrfs-progs`.

### Purpose

This script should make read-only snapshot of desired btrfs subvolumes, and should also help to keep the subvolume list clean asking to remove old and unuseful snapshot.

PAY ATTENTION: this script is tested only on a pair of systems, it should work correctly if you've done snapshot only through this script, but it's not 100% secure.
Read all outputs carefully before proceeding!

### Details

This script wil not take snapshots automagically without your interaction, if you want to have a snapshot you have to run it manually, to have something like a cron job just search for other scripts in github, you'll find it.

The age of a snapshot is measured thanks to the name format: `$SUBVOL_$(date +_%Y-%m-%d_%s)`.
The last string in the name is the UNIX time in seconds, so the script just calculate the difference between the current time and this string.
As you can see in the name there is also the date in a readable format.

It's quite a stupid method but it's simple and, with this name format, snapshots are quite easy to handle also without this script.
