package(default_visibility=['//visibility:public'])
licenses(['notice'])

cc_library(
    name = 'capstone',
    srcs = glob([
        '*.c',
        'arch/*/*.c',
    ]),
    hdrs = glob([
        '*.h',
        'include/*.h',
    ]),
    includes = [
        '.',
        'include',
    ],
)

cc_binary(
    name = 'cstool',
    srcs = glob([
        'cstool/cstool.c',
        'cstool/cstool_*.c',
    ]),
    deps = [
        ':capstone',
    ],
)

[cc_test(
    name = t,
    srcs = [
        'tests/%s.c' % t,
    ],
    deps = [
        ':capstone',
    ],
) for t in [
        'test_basic',
        'test_detail',
        'test_skipdata',
        'test_iter',
        'test_arm',
        'test_arm64',
        'test_mips',
        'test_ppc',
        'test_sparc',
        'test_systemz',
        'test_x86',
        'test_xcore',
    ]
]
