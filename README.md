# SDS File Manager (SFM)

The SDS File Manager (SFM) is a CLI file manager for structured directories (sirectories). It is
available for all major platforms. Just download an appropriate binary and start using.

Notes
	"Dir" would mean directory.
	"PWD" would mean user's present working directory.
	"Subdee" would mean sub-directory.
	"Hidden file" would mean file starting with ".".

## Displaying Contents of A Structured Directory (Sirectory)

SFM allows display of directory contents in an horizontal manner, as well as a vertical a manner.

	Horizontal Manner
		a.txt b.txt c.txt d.txt
		e.txt f.txt g.txt h.txt

	Vertical Manner
		a.txt c.txt e.txt g.txt
		b.txt d.txt f.txt h.txt

SFM also allows the display of dir-content type. Below is an example of a dir's contents displayed,
with the type of its contents also displayed:

	httpd (D), log.txt (F) // This shows that dir-content "httpd" is a dir, and dir-content
		"log.txt" is a file.

#### Syntax
	sfm {A valid-Unix-dir path or ignore if dir is pwd} {Chain of additional commands}

#### Examples
	sfm x // Horizontal display of pwd
	sfm y // Vertical display of pwd
	sfm xt // Horizontal display of pwd, with content type displayed
	sfm yt // Vertical display of pwd, with content type displayed
	sfm someDir x // Horizontal display of a dir not the pwd
	sfm someDir y // Vertical display of a dir not the pwd
	sfm someDir xt // Horizontal display of a dir not the pwd, with content type displayed
	sfm someDir yt // Vertical display of a dir not the pwd, with content type displayed

## Creating New Files and Subdees

SFM allows you to create new files and (sub-directories) subdees:

	- at the beginning of your dir;
	- behind another file/subdee

	sfm cf {New-file name} a // Creating file at the beginning of the dir
	sfm cf {New-file name} b {Old-file name} // Creating file behind another file/subdee
	sfm cf {New-file name} // Creating file without bothering about position

	sfm cd {New-subdee name} a // Creating subdee at the beginning of the dir
	sfm cd {New-subdee name} b {Old file name} // Creating subdee behind another file/subdee
	sfm cd {New-subdee name} // Creating subdee without bothering about position

## Moving Files and Subdees

SFM allows you to move files and subdees about. Movements can be performed only within your present
working directory. Files and subdees can be moved:

	- to the beginning of your dir;
	- behind another file/subdee

	sfm mv {File name or subdee name} a // Moving to The Beginning of The Dir
	sfm mv {File name or subdee name} b {Other file} // Moving to The Back of Another
		File/Subdee

## Directory Segregation

In traditional file managers, files and directories are often segregated. That is, the subdees are
listed before or after listing the files in the dir. Examples of a segregated dir:

	a (file), d (file), f (file), B (dir), C (dir), Z (dir) // Note how the subdees are listed
		after the files.
	E (dir), S (dir), W (dir), r (file), t (file), y (file) // Note how the files are listed
		after the subdees.

SFM however allows files and subdees to mix freely (with the help of the "mv" command). For instance,
the examples above can respectively be reorganized into the following:

	a (file), B (dir), C (dir), d (file), f (file), Z (dir)
	E (dir), r (file), S (dir), t (file), W (dir), y (file)

Assuming the files and subdees in your dir are mixed, the following command can be used to
resegregate them:

	sfm sg da // Subdees would be listed after the files.
	sfm sg db // Subdees would be listed before files.

## Moving Files and Subdees (Revisited)

If command "sfm mv {File name} a" or "sfm mv {File name} z" is performed for a file in a structured
dir, the file would be placed at the beginning of the files section, not necessarily the beginning
of the dir. The same goes for subdees.

## Getting An SDS Dir's Basic Info

How can you know if an SDS directory is segregated? How can you learn some basic info about an SDS
dir? Well, by issuing the command:

	sfm {A valid-Unix-dir path or ignore if dir is pwd} di

#### Examples
	sfm di // Basic SDS info of pwd
	sfm /etc di // Basic SDS info of "/etc"

## Desegregating a Segregated Dir

	sfm {A valid-Unix-dir path or ignore if dir is pwd} ds

#### Examples
	sfm ds // Desegregation of pwd
	sfm /etc ds // Desegregration of "/etc"

## SFM Help

	sfm hp inf // To get some info about the SFM
	sfm hp doc // To get usage document

## Shortcuts

Note: Shortcuts can change with version.

sfm x  | sfm
sfm xt | sfm t
