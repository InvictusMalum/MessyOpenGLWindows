project('macOpenGL', 'cpp',
  version : '0.1',
  default_options : ['warning_level=3', 'cpp_std=c++14'])

inc = [include_directories('Libraries/include')]

cc = meson.get_compiler('cpp')

glfw = dependency('glfw3', required : false)
links = []
if not glfw.found()
  glfw = subproject('glfw-meson')
  links += glfw.get_variable('glfw_library')
  inc += include_directories('subprojects/glfw-meson/include')
  inc += include_directories('subprojects/glfw-meson/src')
endif


source_files = ['main.cpp', 'glad.c']

exe = executable('macOpenGL', source_files,
    include_directories : inc,
    link_with : links)
