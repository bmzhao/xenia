workspace(name = "jp_xenia")

new_local_repository(
    name = "x11",
    build_file_content = """
cc_library(
    name = "x11",
    srcs = ["libX11.so"],
    visibility = ["//visibility:public"],
)
""",
    # pkg-config --variable=libdir x11
    path = "/usr/lib/x86_64-linux-gnu",
)

new_local_repository(
    name = "gtk3",
    build_file_content = """
cc_library(
    name = "gtk3",
    srcs = ["usr/lib/x86_64-linux-gnu/libgtk-3.so"],
    # pkg-config --cflags gtk+-x11-3.0 | python -c 'import sys; print sys.stdin.readline().split()'
    # Todo(bmzhao): investigate use of copts here vs includes bazel option
    hdrs = glob(['usr/include/gtk-3.0/**/*.h']) + glob(['usr/include/at-spi2-atk/2.0/**/*.h']) + glob(['usr/include/at-spi-2.0/**/*.h']) + glob(['usr/include/dbus-1.0/**/*.h']) + glob(['usr/lib/x86_64-linux-gnu/dbus-1.0/include/**/*.h']) + glob(['usr/include/gtk-3.0/**/*.h']) + glob(['usr/include/gio-unix-2.0/**/*.h']) + glob(['usr/include/cairo/**/*.h']) + glob(['usr/include/pango-1.0/**/*.h']) + glob(['usr/include/harfbuzz/**/*.h']) + glob(['usr/include/pango-1.0/**/*.h']) + glob(['usr/include/atk-1.0/**/*.h']) + glob(['usr/include/cairo/**/*.h']) + glob(['usr/include/pixman-1/**/*.h']) + glob(['usr/include/freetype2/**/*.h']) + glob(['usr/include/libpng16/**/*.h']) + glob(['usr/include/freetype2/**/*.h']) + glob(['usr/include/libpng16/**/*.h']) + glob(['usr/include/gdk-pixbuf-2.0/**/*.h']) + glob(['usr/include/libpng16/**/*.h']) + glob(['usr/include/glib-2.0/**/*.h']) + glob(['usr/lib/x86_64-linux-gnu/glib-2.0/include/**/*.h']),
    copts = ['-pthread', '-I/usr/include/gtk-3.0', '-I/usr/include/at-spi2-atk/2.0', '-I/usr/include/at-spi-2.0', '-I/usr/include/dbus-1.0', '-I/usr/lib/x86_64-linux-gnu/dbus-1.0/include', '-I/usr/include/gtk-3.0', '-I/usr/include/gio-unix-2.0/', '-I/usr/include/cairo', '-I/usr/include/pango-1.0', '-I/usr/include/harfbuzz', '-I/usr/include/pango-1.0', '-I/usr/include/atk-1.0', '-I/usr/include/cairo', '-I/usr/include/pixman-1', '-I/usr/include/freetype2', '-I/usr/include/libpng16', '-I/usr/include/freetype2', '-I/usr/include/libpng16', '-I/usr/include/gdk-pixbuf-2.0', '-I/usr/include/libpng16', '-I/usr/include/glib-2.0', '-I/usr/lib/x86_64-linux-gnu/glib-2.0/include'],
    # pkg-config --libs gtk+-x11-3.0 | python -c 'import sys; print sys.stdin.readline().split()'
    linkopts = ['-lgtk-3', '-lgdk-3', '-lpangocairo-1.0', '-lpango-1.0', '-latk-1.0', '-lcairo-gobject', '-lcairo', '-lgdk_pixbuf-2.0', '-lgio-2.0', '-lgobject-2.0', '-lglib-2.0'],
	visibility = ["//visibility:public"],
)
""",
    # pkg-config --variable=libdir gtk+-x11-3.0
    path = "/",
)
