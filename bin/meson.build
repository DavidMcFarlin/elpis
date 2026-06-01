prefix = get_option('prefix')

cdata = configuration_data()
cdata.set('VERSION', meson.project_version())
cdata.set('localedir', join_paths(prefix, get_option('localedir')))
cdata.set('pkgdatadir', join_paths(prefix, pkgdatadir))

configure_file(
  input: 'elpis.in',
  output: 'elpis',
  configuration: cdata,
  install: true,
  install_dir: get_option('bindir')
)

elpis = join_paths(meson.build_root(), 'bin/elpis')
run_target('run',
  command: [elpis, '-v'],
  depends: [
    elpis_resources,
    elpis_settings
  ]
)
