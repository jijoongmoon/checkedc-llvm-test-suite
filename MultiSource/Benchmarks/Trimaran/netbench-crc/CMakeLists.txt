set(PROG netbench-crc)
if(LARGE_PROBLEM_SIZE)
  set(RUN_OPTIONS 40000)
else()
  if(SMALL_PROBLEM_SIZE)
    set(RUN_OPTIONS 1000)
  else()
    set(RUN_OPTIONS 12000)
    if(ARCH STREQUAL "XCore")
      set(XCORE_TARGET_NEEDS_MEMORY 256)
    endif()
  endif()
endif()
llvm_multisource()
