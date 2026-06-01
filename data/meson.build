gnome = import('gnome')

bindir = join_paths(get_option('prefix'), get_option('bindir'))
service_conf = configuration_data()
service_conf.set('bindir', bindir)
configure_file(
  input: 'io.github.DavidMcFarlin.Elpis.service.in',
  output: 'io.github.DavidMcFarlin.Elpis.service',
  configuration: service_conf,
  install: true,
  install_dir: join_paths(get_option('datadir'), 'dbus-1/services')
)

elpis_resources = gnome.compile_resources('elpis',
  'io.github.DavidMcFarlin.Elpis.gresource.xml',
  gresource_bundle: true,
  install: true,
  install_dir: pkgdatadir
)

install_data('io.github.DavidMcFarlin.Elpis.gschema.xml',
  install_dir: join_paths(get_option('datadir'), 'glib-2.0/schemas')
)

elpis_desktop = i18n.merge_file(
  input: 'io.github.DavidMcFarlin.Elpis.desktop.in',
  output: 'io.github.DavidMcFarlin.Elpis.desktop',
  type: 'desktop',
  po_dir: '../po',
  install: true,
  install_dir: join_paths(get_option('datadir'), 'applications')
)

elpis_appstream = i18n.merge_file(
  input: 'io.github.DavidMcFarlin.Elpis.metainfo.xml.in',
  output: 'io.github.DavidMcFarlin.Elpis.metainfo.xml',
  po_dir: '../po',
  install: true,
  install_dir: join_paths(get_option('datadir'), 'metainfo')
)

elpis_settings = gnome.compile_schemas()

appstream_util = find_program('appstream-util', required: false)
if appstream_util.found()
  test('Validate appstream file', appstream_util,
    args: ['validate', '--nonet', elpis_appstream]
  )
endif

desktop_utils = find_program('desktop-file-validate', required: false)
if desktop_utils.found()
  test('Validate desktop file', desktop_utils,
    args: [elpis_desktop]
  )
endif

compile_schemas = find_program('glib-compile-schemas', required: false)
if compile_schemas.found()
  test('Validate schema file', compile_schemas,
    args: ['--strict', '--dry-run', meson.current_source_dir()]
  )
endif

gtk_builder_tool = find_program('gtk4-builder-tool', 'gtk-builder-tool', required: false)
if gtk_builder_tool.found()
  ui_files = [
    ['ui', 'AboutElpisDialog.ui'],
    ['ui', 'ElpisWindow.ui'],
    ['ui', 'PreferencesElpisDialog.ui'],
    ['ui', 'SearchDialog.ui'],
    ['ui', 'StationsDialog.ui'],
    ['ui', 'EqDialog.ui'],
    ['gtk', 'help-overlay.ui'],
  ]
  foreach ui_file : ui_files
    test('Validate @0@'.format(ui_file[1]), gtk_builder_tool,
      args: ['validate', join_paths(meson.current_source_dir(), ui_file[0], ui_file[1])]
    )
  endforeach
endif

subdir('icons')
