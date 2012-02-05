This project is a fork of RipRip/clang_complete. I've forked it and hacked it
to get clang_complete working for iOS development. I am not a clang expert.
Your milage may vary, but I hope this fork may save someone some time.

To install this plugin:

* Install Pathogen [https://github.com/tpope/vim-pathogen]
  (Recommended whenever you're installing any vim plugin.)

* Clone this project into ~/.vim/bundle/

* Add this to your .vimrc:

	filetype on
	autocmd FileType objc  set omnifunc=ClangComplete
	autocmd FileType objc  let g:clang_library_path='/Developer/usr/clang-ide/lib'
	autocmd FileType objc  let g:clang_use_library=1

* Copy the clang_complete.ios_sample.txt file to $YOUR_XCODE_PROJECT_ROOT/.clang_complete.

* Edit that file.

  * If your project uses a .pch file, append:

	-include <ABSOLUTE_PATH_TO_YOUR_DOT_PCH_FILE>

  * If your project has custom "Header Search Path"s, append:

	-I<ABSOLUTE_PATH>
	-I<ABSOLUTE_PATH>
	-I<ABSOLUTE_PATH>
	...

YMMV.
