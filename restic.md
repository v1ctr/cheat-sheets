# Restic Cheat Sheet

## Installation

MacOS
    
    brew install restic

CentOS

    yum install yum-plugin-copr
    yum copr enable copart/restic
    yum install restic

## Preparing a new repository

Local

    restic init --repo <repo-dir>

## Backing up

    restic -r <repo-dir> --verbose backup <backup-dir>

## Verify repository

    restic check -r <repo-dir>

## Working with repositories

Listing all snapshots

    restic -r <repo-dir> snapshots

