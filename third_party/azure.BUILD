# Description:
#   azure-storage-fuse implements a FUSE filesystem for blob storage

licenses(["notice"])

cc_library(
    name = "azure",
    srcs = [
        "include/append_block_request_base.h",
        "include/base64.h",
        "include/blob/append_block_request.h",
        "include/blob/blob_client.h",
        "include/blob/copy_blob_request.h",
        "include/blob/create_block_blob_request.h",
        "include/blob/create_container_request.h",
        "include/blob/delete_blob_request.h",
        "include/blob/delete_container_request.h",
        "include/blob/download_blob_request.h",
        "include/blob/get_blob_property_request.h",
        "include/blob/get_block_list_request.h",
        "include/blob/get_container_property_request.h",
        "include/blob/get_page_ranges_request.h",
        "include/blob/list_blobs_request.h",
        "include/blob/list_containers_request.h",
        "include/blob/put_block_list_request.h",
        "include/blob/put_block_request.h",
        "include/blob/put_page_request.h",
        "include/common.h",
        "include/compare.h",
        "include/constants.h",
        "include/copy_blob_request_base.h",
        "include/create_container_request_base.h",
        "include/delete_blob_request_base.h",
        "include/delete_container_request_base.h",
        "include/executor.h",
        "include/get_blob_property_request_base.h",
        "include/get_blob_request_base.h",
        "include/get_block_list_request_base.h",
        "include/get_container_property_request_base.h",
        "include/get_page_ranges_request_base.h",
        "include/hash.h",
        "include/http/libcurl_http_client.h",
        "include/http_base.h",
        "include/list_blobs_request_base.h",
        "include/list_containers_request_base.h",
        "include/logging.h",
        "include/put_blob_request_base.h",
        "include/put_block_list_request_base.h",
        "include/put_block_request_base.h",
        "include/put_page_request_base.h",
        "include/retry.h",
        "include/storage_EXPORTS.h",
        "include/storage_account.h",
        "include/storage_credential.h",
        "include/storage_errno.h",
        "include/storage_outcome.h",
        "include/storage_request_base.h",
        "include/storage_stream.h",
        "include/storage_url.h",
        "include/tinyxml2.h",
        "include/tinyxml2_parser.h",
        "include/todo/get_blob_metadata_request.h",
        "include/todo/get_blob_properties_request.h",
        "include/todo/query_entities_request.h",
        "include/todo/set_blob_metadata_request.h",
        "include/utility.h",
        "include/xml_parser_base.h",
        "include/xml_writer.h",
        "src/append_block_request_base.cpp",
        "src/base64.cpp",
        "src/blob/blob_client.cpp",
        "src/blob/blob_client_wrapper.cpp",
        "src/constants.cpp",
        "src/copy_blob_request_base.cpp",
        "src/create_container_request_base.cpp",
        "src/delete_blob_request_base.cpp",
        "src/delete_container_request_base.cpp",
        "src/get_blob_property_request_base.cpp",
        "src/get_blob_request_base.cpp",
        "src/get_block_list_request_base.cpp",
        "src/get_container_property_request_base.cpp",
        "src/get_page_ranges_request_base.cpp",
        "src/hash.cpp",
        "src/http/libcurl_http_client.cpp",
        "src/list_blobs_request_base.cpp",
        "src/list_containers_request_base.cpp",
        "src/logging.cpp",
        "src/put_blob_request_base.cpp",
        "src/put_block_list_request_base.cpp",
        "src/put_block_request_base.cpp",
        "src/put_page_request_base.cpp",
        "src/storage_account.cpp",
        "src/storage_credential.cpp",
        "src/storage_url.cpp",
        "src/tinyxml2.cpp",
        "src/tinyxml2_parser.cpp",
        "src/utility.cpp",
    ],
    hdrs = [
        "include/blob/blob_client.h",
    ],
    copts = ["-std=c++11"],
    defines = [
        "USE_OPENSSL",
    ],
    includes = ["include"],
    textual_hdrs = [
        "include/constants.dat",
    ],
    visibility = ["//visibility:public"],
    deps = [
        "@boringssl//:crypto",
        "@curl",
    ] + select({
        "@bazel_tools//src/conditions:darwin": [],
        "//conditions:default": [
            "@util_linux//:uuid",
        ],
    }),
)
