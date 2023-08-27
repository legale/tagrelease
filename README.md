# Versioning Script

A Python script for managing versioning and generating release notes based on commit history.

## Overview

This script automates the process of managing software versions and generating release notes. It does the following:

- Updates the version numbers in a `.version` file based on commit history.
- Categorizes commits as either bug fixes or new features.
- Calculates the release type (major, minor, patch) based on commit categories.
- Generates release notes based on commit messages.
- Tags the repository with a version tag and includes release notes.
- Updates the `CHANGELOG.md` file with the latest release information.

## Usage

### Update Current Version

To update the current version based on commit history, run the script with the `--update` or `-u` flag:

```sh
./tagrelease --update
```

This command will analyze the commit history, calculate the new version, update the `.version` file, and print the updated version.

### Release a New Version

To release a new version, run the script with the `--release` or `-r` flag:

```sh
./tagrelease --release
```

The script will automatically detect the release type (major, minor, or patch) based on commit history. Alternatively, you can force a specific release type using the `--type` or `-t` flag:

```sh
./tagrelease --release --type MAJOR
```

This will generate release notes, create a version tag, update the `CHANGELOG.md` file, and update the `.version` file.

### Dry Run Mode

You can perform a dry run to simulate a version release without actually making any changes. This can help you preview the changes that would be applied:

```sh
./tagrelease --release --dry
```

### Get Current Version

To retrieve the current version without making any changes, simply run the script without any flags:

```sh
./tagrelease
```

## Examples

Update the current version:

```sh
./tagrelease --update
```

Release a new version with automatic release type detection:

```sh
./tagrelease --release
```

Release a new major version:

```sh
./tagrelease --release --type MAJOR
```

Perform a dry run to preview changes without actually releasing:

```sh
./tagrelease --release --dry
```

Get the current version:

```sh
./tagrelease
```

## extra examples
### if release is created already
```sh
ruslan@radar-prod1:~/tagrelease$ ./tagrelease -r
Current version:     1.4.0-0 hash: 3993237

Generating release notes...
Autodetection release type...
        features: 0
        bugs: 0
        else: 0
Detected release type: REVISION
Release new version: 1.4.0-0
Creating release tag... on commit 3993237
Tagging failed with error code: 128
 fatal: tag 'v1.4.0-0' already exists

Unable to continue. Aborting...
```

### update
```sh
ruslan@radar-prod1:~/tagrelease$ ./tagrelease -u
Already up to date.
Current version: 1.4.0-0
```

### remove tag and make release again
```sh
ruslan@radar-prod1:~/tagrelease$ git tag -d v1.4.0-0
Deleted tag 'v1.4.0-0' (was 05d0482)
ruslan@radar-prod1:~/tagrelease$ ./tagrelease -r
Current version:     v1.3.0-0 release commit hash: 61359f7

Generating release notes...
Autodetection release type...
        features: 1
        bugs: 0
        else: 0
Detected release type: MINOR
Release new version: 1.4.0-0
Creating release tag... on commit 3993237
Tagging was successful.
Updating CHANGELOG.md
Updating .version file
Already up to date.
Current version: v1.4.0-0
ruslan@radar-prod1:~/tagrelease$ 
```
#### CHANGELOG.md after release
```md
# CHANGELOG
## v1.4.0-0 28-08-2023 MINOR RELEASE
### features:
- [399323781e60845026c843366a3cd9407fc4c761] [feat] первая рабочая версия
```


As you can see below all releases commits are tagged:
```sh
ruslan@radar-prod1:~/tagrelease$ git lg2
* 0ad02f2 - Mon, 28 Aug 2023 02:44:38 +0300 (3 minutes ago) (HEAD -> master, origin/master)
|           [style] minor print changes - Isaev Ruslan
* 3993237 - Mon, 28 Aug 2023 01:57:14 +0300 (51 minutes ago)
|           [feat] первая рабочая версия - Isaev Ruslan
| * 61359f7 - Mon, 28 Aug 2023 01:57:14 +0300 (51 minutes ago) (tag: v1.3.0-0)
|/            [feat] первая рабочая версия - Isaev Ruslan
* 01e8c0a - Mon, 28 Aug 2023 01:34:15 +0300 (74 minutes ago) (tag: v1.2.0-0)
|           [feat] функция административного отключения вещания ssid - Isaev Ruslan
* c626d6c - Mon, 28 Aug 2023 00:03:28 +0300 (3 hours ago) (tag: v1.1.1-0)
|           14 - Isaev Ruslan
* af653a5 - Sun, 27 Aug 2023 23:37:34 +0300 (3 hours ago) (tag: v1.1.0-0)
|           [chore] Оптимизирован код обработки событий в контроллере для снижения нагрузки на процессор - Isaev Ruslan
* 3b01510 - Sun, 27 Aug 2023 23:37:05 +0300 (3 hours ago)
|           [feat] Новая функция массовой активации WiFi точек доступа для упрощения масштабирования сети - Isaev Ruslan
* b9d864b - Sun, 27 Aug 2023 23:36:31 +0300 (3 hours ago)
|           [fix] Исправлена ошибка, приводящая к периодическим сбоям  в работе контроллера точек доступа - Isaev Ruslan
* a0bd065 - Sun, 27 Aug 2023 23:36:05 +0300 (3 hours ago) (tag: v1.0.0-0)
|           [feat] Внедрена поддержка WPA3 для повышения безопасности ваших WiFi сетей - Isaev Ruslan
* 3c3009b - Sun, 27 Aug 2023 23:35:32 +0300 (3 hours ago)
|           [docs] Обновлена документация по настройке и установке контроллера WiFi точек доступа - Isaev Ruslan
* 24686ba - Sun, 27 Aug 2023 23:35:00 +0300 (3 hours ago)
|           [feat] Добавлена возможность удаленного управления настройками QoS для WiFi точек доступа - Isaev Ruslan
* ab9ea52 - Sun, 27 Aug 2023 23:34:15 +0300 (3 hours ago)
|           [fix] Исправлена утечка памяти, возникающая при длительной работе контроллера в средах высокой загрузки - Isaev Ruslan
* fff5812 - Sun, 27 Aug 2023 23:33:31 +0300 (3 hours ago)
|           [feat!] улучшение производительности в контроллере точек доступа - Isaev Ruslan
* 54ee94f - Sun, 27 Aug 2023 23:32:33 +0300 (3 hours ago)
|           [fix] неправильной обработкой паролей при настройке WiFi точек доступа - Isaev Ruslan
* a7fdacf - Sun, 27 Aug 2023 23:31:31 +0300 (3 hours ago) (tag: v0.1.0-0)
|           [feat] Добавлена поддержка множественных SSID в контроллере WiFi точек доступа - Isaev Ruslan
* 37796b3 - Sun, 27 Aug 2023 19:26:51 +0300 (7 hours ago)
|           We have to move to use git clone as there are no newer tagged releases. - Isaev Ruslan
* 410d2ab - Sun, 27 Aug 2023 15:49:39 +0300 (11 hours ago)
|           [feat]: initialized  to release 1.0.0 - Isaev Ruslan
* 1297403 - Sun, 27 Aug 2023 15:38:38 +0300 (11 hours ago)
|           [fix]: bug wrong return in whateverfunc() - Isaev Ruslan
* f507f66 - Sun, 27 Aug 2023 15:28:10 +0300 (11 hours ago) (tag: v0.0.1-0)
|           [fix]: fix bug 2 - Isaev Ruslan
| *   c038970 - Sun, 27 Aug 2023 20:14:52 +0300 (7 hours ago) (refs/stash)
| |\            WIP on master: f016908 We have to move to use git clone as there are no newer tagged releases. - Isaev Ruslan
|           [fix] Исправлена утечка памяти, возникающая при длительной работе контроллера в средах высокой загрузки - Isaev Ruslan
* fff5812 - Sun, 27 Aug 2023 23:33:31 +0300 (3 hours ago)
|           [feat!] улучшение производительности в контроллере точек доступа - Isaev Ruslan
* 54ee94f - Sun, 27 Aug 2023 23:32:33 +0300 (3 hours ago)
|           [fix] неправильной обработкой паролей при настройке WiFi точек доступа - Isaev Ruslan
* a7fdacf - Sun, 27 Aug 2023 23:31:31 +0300 (3 hours ago) (tag: v0.1.0-0)
|           [feat] Добавлена поддержка множественных SSID в контроллере WiFi точек доступа - Isaev Ruslan
* 37796b3 - Sun, 27 Aug 2023 19:26:51 +0300 (7 hours ago)
|           We have to move to use git clone as there are no newer tagged releases. - Isaev Ruslan
* 410d2ab - Sun, 27 Aug 2023 15:49:39 +0300 (11 hours ago)
|           [feat]: initialized  to release 1.0.0 - Isaev Ruslan
* 1297403 - Sun, 27 Aug 2023 15:38:38 +0300 (11 hours ago)
|           [fix]: bug wrong return in whateverfunc() - Isaev Ruslan
* f507f66 - Sun, 27 Aug 2023 15:28:10 +0300 (11 hours ago) (tag: v0.0.1-0)
|           [fix]: fix bug 2 - Isaev Ruslan
| *   c038970 - Sun, 27 Aug 2023 20:14:52 +0300 (7 hours ago) (refs/stash)
| |\            WIP on master: f016908 We have to move to use git clone as there are no newer tagged releases. - Isaev Ruslan
| | * 21ebc99 - Sun, 27 Aug 2023 20:14:52 +0300 (7 hours ago)
| |/            index on master: f016908 We have to move to use git clone as there are no newer tagged releases. - Isaev Ruslan
| * f016908 - Sun, 27 Aug 2023 19:26:51 +0300 (7 hours ago)
| |           We have to move to use git clone as there are no newer tagged releases. - Isaev Ruslan
| * c94f323 - Sun, 27 Aug 2023 15:49:39 +0300 (11 hours ago)
| |           initialized  to release 1.0.0 - Isaev Ruslan
| * 42bd00b - Sun, 27 Aug 2023 15:38:38 +0300 (11 hours ago)
| |           fix: wrong return in whateverfunc() - Isaev Ruslan
| * 1032102 - Sun, 27 Aug 2023 15:28:10 +0300 (11 hours ago)
|/            2 - Isaev Ruslan
* 9d2f269 - Sun, 27 Aug 2023 15:27:56 +0300 (11 hours ago)
            1 - Isaev Ruslan
```

## script generated CHANGELOG.md based on commits messages
[CHANGELOG_.md](./CHANGELOG_.md) example

## Notes

- This script assumes the existence of a `.version` file with the format `MAJOR=x\nMINOR=y\nPATCH=z\nREVISION=w`.
- Make sure to provide the necessary permissions for the script to write to files and execute Git commands.
- Always review the changes before releasing a new version.
