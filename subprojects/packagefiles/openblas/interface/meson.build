interface_args = []
# if not build_without_cblas
#   interface_args += '-DCBLAS'
# endif
_blas_roots = [
  # NOTE: q, qx, x, xq do not have cblas_ rules in the Makefile
  # NOTE: https://developer.arm.com/documentation/101004/2310/BLAS-Basic-Linear-Algebra-Subprograms/CBLAS-functions?lang=en
  # Level 1
  {
    'base': '?asum',
    '_types': ['s', 'd', 'q', 'sc', 'dz', 'qx'],
    'fname': 'asum.c',
    'cblas': true,
  },
  {
    'base': '?sum',
    '_types': ['s', 'd', 'q', 'sc', 'dz', 'qx'],
    'fname': 'sum.c',
    'cblas': true,
  },
  {
    'base': '?amax',
    '_types': ['s', 'd', 'q', 'sc', 'dz', 'qx'],
    'fname': 'max.c',
    'cblas': true,
  },
  {
    'base': '?amin',
    '_types': ['s', 'd', 'q', 'sc', 'dz', 'qx'],
    'fname': 'max.c',
    'cblas': true,
  },
  {
    'base': '?max',
    '_types': ['s', 'd', 'q'],
    'fname': 'max.c',
  },
  {
    'base': '?min',
    '_types': ['s', 'd', 'q'],
    'fname': 'max.c',
  },
  {
    'base': '?axpy',
    '_types': ['s', 'd', 'q'],
    'fname': 'axpy.c',
    'cblas': true,
  },
  {
    'base': '?axpy',
    '_types': ['c', 'z', 'x'],
    'fname': 'zaxpy.c',
    'cblas': true,
  },
  {
    'base': '?axpyc',
    '_types': ['c', 'z', 'x'],
    'fname': 'zaxpy.c',
    'cblas': true,
  },
  {
    'base': '?copy',
    '_types': ['s', 'd', 'q', 'c', 'z', 'x'],
    'fname': 'copy.c',
    'cblas': true,
  },
  {
    'base': '?dot',
    '_types': ['s', 'd', 'q'],
    'fname': 'dot.c',
    'cblas': true,
  },
  {
    'base': '?dotu',
    '_types': ['c', 'z', 'x'],
    'fname': 'zdot.c',
    'cblas': true,
  },
  {
    'base': '?dotc',
    '_types': ['c', 'z', 'x'],
    'fname': 'zdot.c',
    'cblas': true,
  },
  {
    'base': 'cblas_?dotu_sub',
    '_types': ['c', 'z'],
    'fname': 'zdot.c',
    'cblas': false,  # These don't non-cblas rules Makefile:1623:1627
  },
  {
    'base': 'cblas_?dotc_sub',
    '_types': ['c', 'z'],
    'fname': 'zdot.c',
    'cblas': false,  # These don't non-cblas rules Makefile:1623:1627
  },
  {
    'base': '?nrm2',
    '_types': ['s', 'd', 'q', 'sc', 'dz', 'qx'],
    'fname': 'nrm2.c',
    'cblas': true,  # q, qx don't have cblas_ rules Makefile:1635,1645
  },
  {
    'base': '?rot',
    '_types': ['s', 'd', 'q'],
    'fname': 'rot.c',
    'cblas': true,  # q doesn't have cblas_
  },
  {
    'base': '?rot',
    '_types': ['cs', 'zd', 'xq'],
    'fname': 'zrot.c',
    'cblas': true,
  },
  {
    'base': '?rotm',
    '_types': ['s', 'd', 'q'],
    'fname': 'rotm.c',
    'cblas': true,
  },
  {
    'base': '?rotmg',
    '_types': ['s', 'd', 'q'],
    'fname': 'rotmg.c',
    'cblas': true,
  },
  {
    'base': '?rotg',
    '_types': ['s', 'd', 'q'],
    'fname': 'rotg.c',
    'cblas': true,
  },
  {
    'base': '?rotg',
    '_types': ['c', 'z', 'x'],
    'fname': 'zrotg.c',
    'cblas': true,
  },
  {
    'base': '?scal',
    '_types': ['s', 'd', 'q'],
    'fname': 'scal.c',
    'cblas': true,
  },
  {
    'base': '?scal',
    '_types': ['c', 'z', 'x'],
    'fname': 'zscal.c',
    'cblas': true,  # x doesn't have cblas_
  },
  {
    'base': '?scal',
    '_types': ['cs', 'zd', 'xq'],
    'fname': 'zscal.c',
    'def': ['SSCAL'],
    'undef': [],
    'cblas': true,
  },
  {
    'base': '?swap',
    '_types': ['s', 'd', 'q'],
    'fname': 'swap.c',
    'cblas': true,
  },
  {
    'base': '?swap',
    '_types': ['c', 'z', 'x'],
    'fname': 'zswap.c',
    'cblas': true,
  },
  {
    'base': '?dsdot',
    '_types': ['s'],
    'fname': 'sdsdot.c',
    'cblas': true,
  },
  {
    'base': '?dsdot',
    '_types': [''],
    'fname': 'dsdot.c',
    'cblas': true,
  },
  # TODO: Handle BFLOAT16 Makefile 784:795, 1592:1603
  {
    'base': 'i?max',
    '_types': ['s', 'd', 'q', 'c', 'z'],  # NOTE: c,z only for cblas, Makefile:1526
    'fname': 'imax.c',
    'cblas': true,  # TODO: Maybe 'cblas_only': ['c', 'z']
  },
  {
    'base': 'i?amax',
    '_types': ['s', 'd', 'q', 'c', 'z', 'x'],
    'fname': 'imax.c',
    'cblas': true,
  },
  {
    'base': 'i?amin',
    '_types': ['s', 'd', 'c', 'z', 'x'],
    'fname': 'imax.c',
    'cblas': true,
  },
  {
    'base': 'i?min',
    '_types': ['s', 'd', 'q', 'c', 'z'],  # NOTE: c,z only for cblas, Makefile:1532
    'fname': 'imax.c',
    'cblas': true,
  },
  # Level 2
  {
    'base': '?ger',
    '_types': ['s', 'd', 'q'],
    'fname': 'ger.c',
    'cblas': true,
  },
  {
    'base': '?geru',
    '_types': ['c', 'z', 'x'],
    'fname': 'zger.c',
    'cblas': true,
  },
  {
    'base': '?gerc',
    '_types': ['c', 'z', 'x'],
    'fname': 'zger.c',
    'cblas': true,
  },
  # TODO: Handle BFLOAT16 Makefile 941:944
  # TODO: Handle Netlib_gemv Makefile 946:958
  {
    'base': '?gemv',
    '_types': ['s', 'd', 'q'],
    'fname': 'gemv.c',
    'cblas': true,
  },
  {
    'base': '?gemv',
    '_types': ['c', 'z', 'x'],
    'fname': 'zgemv.c',
    'cblas': true,
  },
  {
    'base': '?trmv',
    '_types': ['s', 'd', 'q'],
    'fname': 'trmv.c',
    'cblas': true,
  },
  {
    'base': '?trmv',
    '_types': ['c', 'z', 'x'],
    'fname': 'ztrmv.c',
    'cblas': true,
  },
  {
    'base': '?trsv',
    '_types': ['s', 'd', 'q'],
    'fname': 'trsv.c',
    'cblas': true,
  },
  {
    'base': '?trsv',
    '_types': ['c', 'z', 'x'],
    'fname': 'ztrsv.c',
    'cblas': true,
  },
  # TODO: Handle NO_LAPACK
  {
    'base': '?symv',
    '_types': ['s', 'd', 'q'],
    'fname': 'symv.c',
    'cblas': true,
  },
  {
    'base': '?symv',
    '_types': ['c', 'z', 'x'],
    'fname': 'zsymv.c',
    'cblas': false,  # NOTE: This oddly has no cblas set..
  },
  {
    'base': '?syr',
    '_types': ['s', 'd', 'q'],
    'fname': 'syr.c',
    'cblas': true,
  },
  {
    'base': '?syr',
    '_types': ['c', 'z', 'x'],
    'fname': 'zsyr.c',
    'cblas': false,  # NOTE: This oddly has no cblas set..
  },
  {
    'base': '?syr2',
    '_types': ['s', 'd', 'q'],
    'fname': 'syr2.c',
    'cblas': true,
  },
  {
    'base': '?syr2',
    '_types': ['c', 'z', 'x'],
    'fname': 'zsyr2.c',
    'cblas': false,  # NOTE: This oddly has no cblas set..
  },
  {
    'base': '?gbmv',
    '_types': ['s', 'd', 'q'],
    'fname': 'gbmv.c',
    'cblas': true,
  },
  {
    'base': '?gbmv',
    '_types': ['c', 'z', 'x'],
    'fname': 'zgbmv.c',
    'cblas': true,
  },
  {
    'base': '?sbmv',
    '_types': ['s', 'd', 'q'],
    'fname': 'sbmv.c',
    'cblas': true,
  },
  {
    'base': '?sbmv',
    '_types': ['c', 'z', 'x'],
    'fname': 'zsbmv.c',
    'cblas': false,  # NOTE: This oddly has no cblas set..
  },
  {
    'base': '?spmv',
    '_types': ['s', 'd', 'q'],
    'fname': 'spmv.c',
    'cblas': true,
  },
  # TODO: NO_LAPACK
  {
    'base': '?spmv',
    '_types': ['c', 'z', 'x'],
    'fname': 'zspmv.c',
    'cblas': false,  # NOTE: This oddly has no cblas set..
  },
  {
    'base': '?spr',
    '_types': ['s', 'd', 'q'],
    'fname': 'spr.c',
    'cblas': true,
  },
  {
    'base': '?spr',
    '_types': ['c', 'z', 'x'],
    'fname': 'zspr.c',
    'cblas': false,  # NOTE: This oddly has no cblas set..
  },
  {
    'base': '?spr2',
    '_types': ['s', 'd', 'q'],
    'fname': 'spr2.c',
    'cblas': true,
  },
  {
    'base': '?spr2',
    '_types': ['c', 'z', 'x'],
    'fname': 'zspr2.c',
    'cblas': false,  # NOTE: This oddly has no cblas set..
  },
  {
    'base': '?tbmv',
    '_types': ['s', 'd', 'q'],
    'fname': 'tbmv.c',
    'cblas': true,
  },
  {
    'base': '?tbmv',
    '_types': ['c', 'z', 'x'],
    'fname': 'ztbmv.c',
    'cblas': true,
  },
  {
    'base': '?tbsv',
    '_types': ['s', 'd', 'q'],
    'fname': 'tbsv.c',
    'cblas': true,
  },
  {
    'base': '?tbsv',
    '_types': ['c', 'z', 'x'],
    'fname': 'ztbsv.c',
    'cblas': true,
  },
  {
    'base': '?tpsv',
    '_types': ['s', 'd', 'q'],
    'fname': 'tpsv.c',
    'cblas': true,
  },
  {
    'base': '?tpsv',
    '_types': ['c', 'z', 'x'],
    'fname': 'ztpsv.c',
    'cblas': true,
  },
  {
    'base': '?tpmv',
    '_types': ['s', 'd', 'q'],
    'fname': 'tpmv.c',
    'cblas': true,
  },
  {
    'base': '?tpmv',
    '_types': ['c', 'z', 'x'],
    'fname': 'ztpmv.c',
    'cblas': true,
  },
  {
    'base': '?hemv',
    '_types': ['c', 'z', 'x'],
    'fname': 'zhemv.c',
    'cblas': true,
  },
  {
    'base': '?hbmv',
    '_types': ['c', 'z', 'x'],
    'fname': 'zhbmv.c',
    'cblas': true,
  },
  {
    'base': '?her',
    '_types': ['c', 'z', 'x'],
    'fname': 'zher.c',
    'cblas': true,
  },
  {
    'base': '?her2',
    '_types': ['c', 'z', 'x'],
    'fname': 'zher2.c',
    'cblas': true,
  },
  {
    'base': '?hpmv',
    '_types': ['c', 'z', 'x'],
    'fname': 'zhpmv.c',
    'cblas': true,
  },
  {
    'base': '?hpr',
    '_types': ['c', 'z', 'x'],
    'fname': 'zhpr.c',
    'cblas': true,
  },
  {
    'base': '?hpr2',
    '_types': ['c', 'z', 'x'],
    'fname': 'zhpr2.c',
    'cblas': true,
  },
  # TODO: BUILD_BFLOAT16 here, Makefile:1303
  {
    'base': '?gemm',
    '_types': ['s', 'd', 'q', 'c', 'z', 'x'],
    'fname': ['gemm.c', '../param.h'],  # TODO: Will this work?
    'cblas': true,
  },
  {
    'base': '?gemmt',
    '_types': ['s', 'd', 'q', 'c', 'z', 'x'],
    'fname': ['gemmt.c', '../param.h'],
    'cblas': true,
  },
  {
    'base': '?symm',
    '_types': ['s', 'd', 'q', 'c', 'z', 'x'],
    'fname': 'symm.c',
    'cblas': true,
  },
  {
    'base': '?trmm',
    '_types': ['s', 'd', 'q', 'c', 'z', 'x'],
    'fname': 'trsm.c',
    'def': ['TRMM'],
    'undef': [],
    'cblas': true,
  },
  {
    'base': '?trsm',
    '_types': ['s', 'd', 'q', 'c', 'z', 'x'],
    'fname': 'trsm.c',
    'cblas': true,
  },
  {
    'base': '?syrk',
    '_types': ['s', 'd', 'q', 'c', 'z', 'x'],
    'fname': 'syrk.c',
    'cblas': true,
  },
  {
    'base': '?syr2k',
    '_types': ['s', 'd', 'q', 'c', 'z', 'x'],
    'fname': 'syr2k.c',
    'cblas': true,
  },
  {
    'base': '?hemm',
    '_types': ['c', 'z', 'x'],
    'fname': 'symm.c',
    'cblas': true,
  },
  {
    'base': '?herk',
    '_types': ['c', 'z', 'x'],
    'fname': 'syrk.c',
    'cblas': true,
  },
  {
    'base': '?her2k',
    '_types': ['c', 'z', 'x'],
    'fname': 'syr2k.c',
    'cblas': true,
  },
  {
    'base': '?gemm3m',
    '_types': ['c', 'z', 'x'],
    'fname': 'gemm.c',
    'cblas': true,
  },
  {
    'base': '?symm3m',
    '_types': ['c', 'z', 'x'],
    'fname': 'symm.c',
  },
  {
    'base': '?hemm3m',
    '_types': ['c', 'z', 'x'],
    'fname': 'symm.c',
  },
  # BLAS Extensions
  {
    'base': '?axpby',
    '_types': ['s', 'd'],
    'fname': 'axpby.c',
    'cblas': true,
  },
  {
    'base': '?axpby',
    '_types': ['c', 'z'],
    'fname': 'zaxpby.c',
    'cblas': true,
  },
  {
    'base': '?omatcopy',
    '_types': ['s', 'd'],
    'fname': 'omatcopy.c',
    'cblas': true,
  },
  {
    'base': '?omatcopy',
    '_types': ['c', 'z'],
    'fname': 'zomatcopy.c',
    'cblas': true,
  },
  {
    'base': '?imatcopy',
    '_types': ['s', 'd'],
    'fname': 'imatcopy.c',
    'cblas': true,
  },
  {
    'base': '?imatcopy',
    '_types': ['c', 'z'],
    'fname': 'zimatcopy.c',
    'cblas': true,
  },
  {
    'base': '?geadd',
    '_types': ['s', 'd'],
    'fname': 'geadd.c',
    'cblas': true,
  },
  {
    'base': '?geadd',
    '_types': ['c', 'z'],
    'fname': 'zgeadd.c',
    'cblas': true,
  },
  {
    'base': '?xerbla',
    '_types': [''],
    'fname': 'xerbla.c',
    'cblas': true,
  },
]

if not is_win and not get_option('build_without_lapack')
  subdir('lapack')
  _blas_roots += _lapack_interface_roots
endif

_interface_libs = []
foreach conf : _blas_roots
  foreach type : conf['_types']
    if 'q' in type or 'x' in type
      # TODO: Figure out when to build these
      # These are the XDOUBLE symbols
      continue
    endif
    # Seed with common args
    compiler_args = _cargs + interface_args
    if fc_id == 'gcc'
      compiler_args += ['-DF_INTERFACE_GFORT']
    endif
    # Generate the symbol flags
    base = conf['base']
    if symb_defs.has_key(base)
      symb_base = symb_defs[base]
      if symb_base.has_key('def')
        foreach _d : symb_base['def']
          compiler_args += ('-D' + _d)
        endforeach
      endif
      if symb_base.has_key('undef')
        foreach _u : symb_base['undef']
          compiler_args += ('-U' + _u)
        endforeach
      endif
    endif
    # Set the type arguments
    if precision_mappings.get(type).has_key('def')
      foreach d : precision_mappings[type]['def']
        compiler_args += ['-D' + d]
      endforeach
    endif
    if precision_mappings.get(type).has_key('undef')
      foreach u : precision_mappings[type]['undef']
        compiler_args += ['-U' + u]
      endforeach
    endif

    if conf.has_key('addl')
      compiler_args += conf['addl']
    endif

    # Construct the actual symbol names, and mangled symbols
    # TODO: This might be conditional on other options
    sym_name = conf['base'].replace('?', type)
    sym_underscored = f'@sym_name@_'
    if conf.get('cblas', false)
      cblas_sym_name = 'cblas_' + sym_name
      cblas_sym_underscored = f'@cblas_sym_name@_'
    endif

    # Construct conditionals
    if conf.has_key('def')
      foreach d : conf['def']
        compiler_args += ['-D' + d]
      endforeach
      foreach u : conf['undef']
        compiler_args += ['-U' + u]
      endforeach
    endif

    # Make mangled symbols
    # TODO: This might be conditional on other options

    # Create the static library for each symbol
    lib = static_library(
      sym_name,
      sources: conf['fname'],
      include_directories: _inc,
      c_args: compiler_args + [
        f'-DASMNAME=@asm_name_prefix@@sym_name@',
        f'-DASMFNAME=@asm_name_prefix@@sym_underscored@',
        f'-DNAME=@sym_underscored@',
        f'-DCNAME=@sym_name@',
        f'-DCHAR_NAME="@sym_underscored@"',
        f'-DCHAR_CNAME="@sym_name@"',
      ],
    )
    _interface_libs += lib

    # If it's a CBLAS symbol, also create that
    if conf.get('cblas', false)
      if 'q' in type or 'x' in type
        # There are no cblas_q symbols
        # TODO: Handle edge cases around dz zd sc
        continue
      endif
      cblas_lib = static_library(
        cblas_sym_name,
        sources: conf['fname'],
        include_directories: _inc,
        c_args: compiler_args + [
          '-DCBLAS',
          f'-DASMNAME=@asm_name_prefix@@cblas_sym_name@',
          f'-DASMFNAME=@asm_name_prefix@@cblas_sym_underscored@',
          f'-DNAME=@cblas_sym_underscored@',
          f'-DCNAME=@cblas_sym_name@',
          f'-DCHAR_NAME="@cblas_sym_underscored@"',
          f'-DCHAR_CNAME="@cblas_sym_name@"',
        ],
      )
      _interface_libs += cblas_lib
    endif
  endforeach
endforeach

# Create a combined static library linking all individual static libraries
_interface = static_library(
  '_interface',
  link_whole: _interface_libs,
)
