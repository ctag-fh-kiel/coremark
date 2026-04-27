idf_component_register(	SRCS "main.c" 
							"core_list_join.c"
							"core_main.c"
							"core_matrix.c"
							"core_portme.c"
							"core_state.c"
							"core_util.c"
                    	INCLUDE_DIRS "."
                    	LDFRAGMENTS "linker.lf"  # uncomment if you want to map code in IRAM but it does not improve coremark result due to cache I guess.
                    	)

target_compile_options(${COMPONENT_LIB} PRIVATE ${CONFIG_OPTIMIZATION} "-O3" "-funroll-all-loops" "-fgcse-sm" "-finline-limit=500" "-fno-schedule-insns" "-fno-code-hoisting" "-fno-tree-loop-distribution" -D${CONFIG_RUN_TYPE}=1)

