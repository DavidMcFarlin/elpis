sphinx_build = find_program(['sphinx-build-3', 'sphinx-build'], required: false)
if sphinx_build.found()
  custom_target('Elpis docs',
    output: ['html'],
    command: [
      sphinx_build, meson.current_source_dir(), '@OUTPUT@'
    ],
    # https://github.com/mesonbuild/meson/issues/1942
    # build_always: true
  )
endif

help2man = find_program('help2man', required: false)
if help2man.found()
  # Target only for maintainers
  custom_target('Elpis man page',
    depend_files: files('../elpis/application.py'),
    output: 'elpis.1', # TODO: Output into source dir..
    command: [
      # https://github.com/mesonbuild/meson/issues/266
      'env', 'MESON_SOURCE_ROOT=' + meson.source_root(), 'MESON_BUILD_ROOT=' + meson.build_root(),
      help2man, '--no-info', '--output=@OUTPUT@', elpis
    ]
  )
endif

install_man('elpis.1')
