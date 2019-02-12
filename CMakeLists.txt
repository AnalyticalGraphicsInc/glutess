cmake_minimum_required(VERSION 3.1)

project(glutess)

set(_headers
    "dict-list.h"
    "dict.h"
    "geom.h"
    "gluos.h"
    "glutess.h"
    "memalloc.h"
    "mesh.h"
    "normal.h"
    "priorityq-heap.h"
    "priorityq-sort.h"
    "priorityq.h"
    "render.h"
    "sweep.h"
    "tess.h"
    "tessellate.h"
    "tessmono.h"
    )

set(_sources
    "dict.c"
    "geom.c"
    "memalloc.c"
    "mesh.c"
    "normal.c"
    "priorityq.c"
    "priorityq-heap.c"
    "render.c"
    "sweep.c"
    "tess.c"
    "tessellate.c"
    "tessmono.c"
    )

list(SORT _headers)
list(SORT _sources)

source_group(Headers FILES ${_headers})
source_group(Sources FILES ${_sources})

add_library(glutess STATIC ${_headers} ${_sources})
set_target_properties(glutess PROPERTIES DEBUG_POSTFIX "d")
set_target_properties(glutess PROPERTIES POSITION_INDEPENDENT_CODE ON)
