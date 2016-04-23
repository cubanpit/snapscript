# snapscript

Script to simplify btrfs snapshots management.

Use it at your own risk, there is no guarantee that this scripts does not kill you system.

### Purpose

This script should make read-only snapshot of desired btrfs subvolumes, and should also help to keep the subvolume list clean asking to remove old and unuseful snapshot.
PAY ATTENTION: this script is tested only on a single system, it should work correctly if you've done snapshot only through this script, but it's not 100% secure.
Read all outputs carefully before proceeding!

### Details

This script wil not take snapshots automagically without your interaction, if you want to have a snapshot you have to run it manually, to have something like a cron job search for other script in github, you'll find it.

If you set a monthly snapshot of home subvolume, this script will check the month of your previous snapshots and ask you the confirmation for taking a snapshot only when the actual month differs. otherwise it will skip that subvolume.

Example:
 - you take a "monthly" snapshot on 10 april 2016 (month n.4), it's saved as name_$YEAR_$MONTH i.e. name_2016_04;
 - you run the script on 22 april 2016, it looks for a name_2016_04 snapshot, it finds it, it does not ask you to take another one;
 - you run the script again on 2 may 2016 (month n.5), it looks for a name_2016_05 snapshot, it does not find it, it asks you to take another snapshot.

It's quite a stupid method but it's simple and, with this name format, snapshots are easy to handle also without this script.
