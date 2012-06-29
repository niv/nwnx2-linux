find_package(RubyRVM 1.9)

#set(RUBY_FOUND true)
#set(RUBY_INCLUDE_DIRS
#	/usr/local/rvm/rubies/default/include/ruby-1.9.1
#	/usr/local/rvm/rubies/default/include/ruby-1.9.1/i686-linux/
#)
#set(RUBY_LIBRARY
#	/usr/local/rvm/rubies/default/lib/libruby.so
#)

if (RUBY_FOUND)
	include_directories(${RUBY_INCLUDE_DIRS})
	add_module(ruby FunctionHooks ruby_int NWNXRuby plugin-ruby)
	target_link_libraries(ruby ${RUBY_LIBRARY})
else (RUBY_FOUND)
	message(WARNING "Cannot find ruby libraries.")
endif (RUBY_FOUND)
