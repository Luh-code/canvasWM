project('canvasWindowManager', ['c'], version : '0.1')

pkgconfig = import('pkgconfig')

wlroots_dep = dependency('wlroots')
libdrm_header_dep = dependency('libdrm').partial_dependency(compile_args: true, includes: true)
wayland_server_dep = dependency('wayland-server')
libinput_dep = dependency('libinput')
xkbcommon_dep = dependency('xkbcommon')

wayland_scanner_dep = dependency('wayland-scanner')
wayland_protocols_dep = dependency('wayland-protocols')
wayland_scanner = wayland_scanner_dep.get_pkgconfig_variable('wayland_scanner')
wayland_protocols = wayland_protocols_dep.get_pkgconfig_variable('pkgdatadir')

xdg_shell_path = join_paths(wayland_protocols, 'stable/xdg-shell/xdg-shell.xml')
message('xdg_shell_path:', xdg_shell_path)

xdg_shell_protocol_h = custom_target('xdg-shell-protocol.h',
    output : 'xdg-shell-protocol.h',
    command : [wayland_scanner, 'server-header',
               xdg_shell_path,
               '@OUTPUT@'],
    build_by_default : true)

executable('canvasWM',
    ['main.c'],
    dependencies : [wlroots_dep, libdrm_header_dep, wayland_server_dep, libinput_dep, xkbcommon_dep],
    include_directories : include_directories('./builddir/'),
    c_args : ['-DWLR_USE_UNSTABLE'],
    install : true,
    install_dir : './builddir',
    build_by_default : true,
)
