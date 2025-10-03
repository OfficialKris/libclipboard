# libclipboard sample executables

# Set executables
add_executable(clip_sample clipboard_sample.c)

# Link it with libclipboard
target_link_libraries(clip_sample LINK_PUBLIC clipboard)
