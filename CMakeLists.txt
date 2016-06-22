set(GFFCOMPARE_SOURCE_FILES
        ../gclib/GArgs.cpp
        ../gclib/GBase.cpp
        ../gclib/gdna.cpp
        ../gclib/gff.cpp
        ../gclib/GList.hh
        ../gclib/GStr.cpp
        ../gclib/GVec.hh
        ../gclib/GFastaIndex.cpp
        ../gclib/GHash.hh
        ../gclib/GFaSeqGet.cpp
        ../gclib/codons.cpp
        gtf_tracking.cpp
        )
add_executable(gffcompare gffcompare.cpp ${GFFCOMPARE_SOURCE_FILES})
set_target_properties(gffcompare PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${Isoaux_BINDIR})