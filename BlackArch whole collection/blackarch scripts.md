---
title: blackarch scripts
draft: false
tags:
  - notag
date: 2024-10-05
---
Here is a reference for scripts in the scripts/ directory:
• baaur - Soon, this will upload packages to the AUR.
• babuild - Build a package.
• bachroot - Manage a chroot for testing.
• baclean - Clean old .pkg.tar.xz files from the package repo.
• baconflict - Soon this will replace scripts/conflicts.
• bad-files - Find bad files in built packages.
• balock - Obtain or release the package repo lock.
• banotify - Notify IRC about package pushes.
15
The BlackArch Linux Guide
• barelease - Release packages to the package repo.
• baright - Print the BlackArch copyright info.
• basign - Sign packages.
• basign-key - Sign a key.
• blackman - This behaves sort of like pacman but builds from git (not to be confused with nrz’s
Blackman).
• check-groups - Check groups.
• checkpkgs - Check packages for errors.
• conflicts - Check for file conflicts.
• dbmod - Modify a package database.
• depth-list - Create a list sorted by dependency depth.
• deptree - Create a dependency tree, listing only blackarch-provided packages.
• get-blackarch-deps - Get a list of blackarch dependencies for a package.
• get-official - Get official packages for release.
• list-loose-packages - List packages that are not in groups and are not dependencies for other
packages.
• list-needed - List missing dependencies.
• list-removed - List packages that are in the package repo but not in git.
• list-tools - List tools.
• outdated - Look for packages that are out-dated in the package repo relative to the git repo.
• pkgmod - Modify a build package.
• pkgrel - Increment pkgrel in a package.
• prep - Clean up a PKGBUILD file’s style and find errors.
• sitesync - Sync between a local copy of the package repo and a remote copy.
• size-hunt - Hunt for large packages.
• source-backup - Backup package source files.
