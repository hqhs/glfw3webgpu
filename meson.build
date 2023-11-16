project('wgsl3wgpu', 'c', version: '0.0.0', license: 'MIT')
src = ['glfw3webgpu.c', 'glfw3webgpu.h']

host_os_family = host_machine.system()
extra_args = []
extra_link_args = []
if host_os_family == 'darwin'
    extra_link_args += [
        '-L/usr/local/lib',
        '-ldl',
        '-framework', 'IOKit',
        '-framework', 'Cocoa',
        '-framework', 'QuartzCore',
        '-framework', 'CoreVideo',
    ]
    extra_args += ['-x', 'objective-c']
endif

glfw3wgpu_library = library(
    'glfw3webgpu',
    src,
    c_args: extra_args,
    link_args: extra_link_args,
)

glfw3wgpu = declare_dependency(
    link_with: glfw3wgpu_library,
)
