# README #

### What is this repository for? ###

* DBC language syntax highlighting and settings for Sublime 3.0
* Version 0.2

### How do I get set up? ###

Create a dbc directory in sublime packages directory (Preferences -> Browse Packages)
Copy to the files to the dbc directory


## TODO ##

- Primary keywords:
	add
	close, closeall
	debug
	divide
	loadmod
	movefptr
	movelabel
	movelength
	movelptr
	movelv
	movesize
	movevl
	multiply
	replace
	rollout
	scan
	search
	shutdown
	stop
	subtract
	unload
	wait

- File keywords
	deletek
	open
	read
	readgplk
	readkg
	readkglk
	readkgp
	readkp
	readkplk
	readks
	readkslk
	readlk
	write

- Indentation defaults
- Trap functions

- Find a way to override goto-definition word seperators
	Will likely need to create a macro/custom command to replace F12 so that it selects the entire word instead of seperating it by '.'
	https://forum.sublimetext.com/t/problem-with-goto-defintion/26228/6


- Remaining keywords:
	beep
	bump
	change
	clearendkey
	clock
	cmatch
	cmove
	comclr
	comctl
	comopen, comclose
	compare
	compareadr
	comtst
	comwait
	console
	count
	delete
	destroy
	disable
	draw
	edit
	empty
	enable
	endset
	erase
	execute
	extend
	filepi
	flusheof
	format
	fposit
	get
	getcolor
	getcursor
	getendkey
	getglobal
	getlabel
	getmodules
	getname
	getobject
	getpaperbins
	getparm
	getposition
	getprinters
	getwindow
	hide
	insert
	keyin
	lcmove
	lenset
	link
	loadadr
	loadlabel
	loadparm
	make
	makeglobal
	makevar
	match
	mod
	nformat
	noeject
	pause
	ploadmod
	popreturn
	prepare
	pushreturn
	put
	putfirst
	query
	recv
	recvclr
	release
	rename
	reposit
	resetparm
	rotate
	send
	sendclr
	setendkey
	setlptr
	setnull
	sformat
	show
	sound
	splclose
	splopen
	splopt
	sqlcode
	sqlexec
	sqlmsg
	storeadr
	storelabel
	tabpage
	test
	unlink
	unlock
	unpacklist
	updatab
	update
	weof
	xor