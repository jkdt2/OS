# OS F15 Libraries

You will need to build the OS library such that you can dynamic link the OS library to the cached shared libraries on your system.

To do this, please clone the OS repository where you will change directories into the lib directory. In the lib directory, please follow the sequence of commands:

            			mkdir build         [press enter]
			            cd build            [press enter]
						cmake ..            [press enter]
						sudo make install   [press enter]
						sudo ldconfig       [press enter]

After you have completed this, you are all set to begin running programs found in this repository. If you have any problems/errors with these commands above, feel free to shoot me an email: koboldtmichael@gmail.com

Current libraries:
- bitmap (v1.5)
	- It's a bitmap, it stores bits!
	- Wishlist:
		- FLZ/FLS
		- Better FFZ/FFS/for_each
		- Resumeable FFS/FFZ/FLZ/FLS ?
		- Parameter checking
			- Just never give us a bad pointer or bit address and it's fine :p
		- Rename export to data (that's what C++ calls it)???

- dyn_array (v1.2.2)
	- It's a vector, it's a stack, it's a deque, it's all your hopes and dreams!
	- Supports destructors! Function pointers are fun.
	- Wishlist:
		- Better insert_sorted (bsearch-based)
		- shrink_to_fit (add a flag to the struct, have it be read by dyn_request_size_increase)
		- prune (remove those who match a certain criteria (via function pointer))
		- Rename export to data (that's what C++ calls it)???
		- Inserting/removing n objects at a time
		    - Dyn's core already supports this, the API doesn't.
		    	- I didn't want to write more unit tests...

- block_store (v2.0)
	- Generic in-memory block storage system with optional file linking
	- Wishlist:
		- Better testing. Flush testing is a little lighter than I'd like, but I'm tired of looking at it
		- Better utility implementation, block based. Actually, may be better to just offload block work to the OS? (the way it is now)
		- Make in-memory optional, add flag (FILE_BACKED) and detect and switch internal functions if it's set

Eventually (maybe):
- dyn_list
	- It's a list, it stores things!
	- Doubly-linked

- dyn_hash
	- It's a hash table, it stores AND hashes things! Exciting!

-- Will, the best TA
