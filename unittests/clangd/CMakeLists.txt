set(LLVM_LINK_COMPONENTS
  support
  )

get_filename_component(CLANGD_SOURCE_DIR
  ${CMAKE_CURRENT_SOURCE_DIR}/../../clangd REALPATH)
include_directories(
  ${CLANGD_SOURCE_DIR}
  )

add_extra_unittest(ClangdTests
  Annotations.cpp
  ClangdTests.cpp
  ClangdUnitTests.cpp
  CodeCompleteTests.cpp
  CodeCompletionStringsTests.cpp
  ContextTests.cpp
  DraftStoreTests.cpp
  FileIndexTests.cpp
  FuzzyMatchTests.cpp
  GlobalCompilationDatabaseTests.cpp
  HeadersTests.cpp
  IndexTests.cpp
  JSONExprTests.cpp
  SourceCodeTests.cpp
  SymbolCollectorTests.cpp
  SyncAPI.cpp
  TestFS.cpp
  ThreadingTests.cpp
  TraceTests.cpp
  TUSchedulerTests.cpp
  URITests.cpp
  XRefsTests.cpp
  )

target_link_libraries(ClangdTests
  PRIVATE
  clangBasic
  clangDaemon
  clangFormat
  clangFrontend
  clangIndex
  clangLex
  clangSema
  clangTooling
  clangToolingCore
  LLVMSupport
  LLVMTestingSupport
  )
