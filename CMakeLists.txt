
project(xmlsec_example C)
cmake_minimum_required(VERSION 3.12)

add_library(xmlsec INTERFACE )

target_compile_definitions(xmlsec INTERFACE 
	 _CRT_SECURE_NO_WARNINGS
	 XMLSEC_CRYPTO_OPENSSL=1
)



target_include_directories(xmlsec INTERFACE include)
target_link_libraries(xmlsec INTERFACE ${CMAKE_CURRENT_LIST_DIR}/lib/xmlsec.lib)


add_executable(xmlsec_example ${CMAKE_CURRENT_LIST_DIR}/examples/sign2.c  )
target_link_libraries(xmlsec_example PUBLIC xmlsec )
 