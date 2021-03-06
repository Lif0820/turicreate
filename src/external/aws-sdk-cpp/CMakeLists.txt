project(aws-sdk-cpp)

set(_aws_source_file_list
    aws-cpp-sdk-core/source/AmazonSerializableWebServiceRequest.cpp
    aws-cpp-sdk-core/source/AmazonStreamingWebServiceRequest.cpp
    aws-cpp-sdk-core/source/AmazonWebServiceRequest.cpp
    aws-cpp-sdk-core/source/auth/AWSAuthSigner.cpp
    aws-cpp-sdk-core/source/auth/AWSCredentialsProvider.cpp
    aws-cpp-sdk-core/source/auth/AWSCredentialsProviderChain.cpp
    aws-cpp-sdk-core/source/Aws.cpp
    aws-cpp-sdk-core/source/client/AWSClient.cpp
    aws-cpp-sdk-core/source/client/AWSErrorMarshaller.cpp
    aws-cpp-sdk-core/source/client/ClientConfiguration.cpp
    aws-cpp-sdk-core/source/client/CoreErrors.cpp
    aws-cpp-sdk-core/source/client/DefaultRetryStrategy.cpp
    aws-cpp-sdk-core/source/config/AWSProfileConfigLoader.cpp
    aws-cpp-sdk-core/source/external/json-cpp/jsoncpp.cpp
    aws-cpp-sdk-core/source/external/tinyxml2/tinyxml2.cpp
    aws-cpp-sdk-core/source/Globals.cpp
    aws-cpp-sdk-core/source/http/curl/CurlHandleContainer.cpp
    aws-cpp-sdk-core/source/http/curl/CurlHttpClient.cpp
    aws-cpp-sdk-core/source/http/HttpClient.cpp
    aws-cpp-sdk-core/source/http/HttpClientFactory.cpp
    aws-cpp-sdk-core/source/http/HttpRequest.cpp
    aws-cpp-sdk-core/source/http/HttpTypes.cpp
    aws-cpp-sdk-core/source/http/Scheme.cpp
    aws-cpp-sdk-core/source/http/standard/StandardHttpRequest.cpp
    aws-cpp-sdk-core/source/http/standard/StandardHttpResponse.cpp
    aws-cpp-sdk-core/source/http/URI.cpp
    aws-cpp-sdk-core/source/internal/EC2MetadataClient.cpp
    aws-cpp-sdk-core/source/platform/linux-shared/Environment.cpp
    aws-cpp-sdk-core/source/platform/linux-shared/FileSystem.cpp
    aws-cpp-sdk-core/source/platform/linux-shared/OSVersionInfo.cpp
    aws-cpp-sdk-core/source/platform/linux-shared/Security.cpp
    aws-cpp-sdk-core/source/platform/linux-shared/Time.cpp
    aws-cpp-sdk-core/source/platform/linux-shared/UUID_Impl.cpp
    aws-cpp-sdk-core/source/utils/Array.cpp
    aws-cpp-sdk-core/source/utils/base64/Base64.cpp
    aws-cpp-sdk-core/source/utils/crypto/Cipher.cpp
    #aws-cpp-sdk-core/source/utils/crypto/commoncrypto/CryptoImpl.cpp
    aws-cpp-sdk-core/source/utils/crypto/CryptoBuf.cpp
    aws-cpp-sdk-core/source/utils/crypto/CryptoStream.cpp
    aws-cpp-sdk-core/source/utils/crypto/factory/Factories.cpp
    aws-cpp-sdk-core/source/utils/crypto/MD5.cpp
    aws-cpp-sdk-core/source/utils/crypto/openssl/CryptoImpl.cpp
    aws-cpp-sdk-core/source/utils/crypto/Sha256.cpp
    aws-cpp-sdk-core/source/utils/crypto/Sha256HMAC.cpp
    aws-cpp-sdk-core/source/utils/DateTimeCommon.cpp
    aws-cpp-sdk-core/source/utils/EnumParseOverflowContainer.cpp
    aws-cpp-sdk-core/source/utils/GetTheLights.cpp
    aws-cpp-sdk-core/source/utils/HashingUtils.cpp
    aws-cpp-sdk-core/source/utils/json/JsonSerializer.cpp
    aws-cpp-sdk-core/source/utils/logging/AWSLogging.cpp
    aws-cpp-sdk-core/source/utils/logging/ConsoleLogSystem.cpp
    aws-cpp-sdk-core/source/utils/logging/DefaultLogSystem.cpp
    aws-cpp-sdk-core/source/utils/logging/FormattedLogSystem.cpp
    aws-cpp-sdk-core/source/utils/logging/LogLevel.cpp
    aws-cpp-sdk-core/source/utils/memory/AWSMemory.cpp
    aws-cpp-sdk-core/source/utils/stream/ResponseStream.cpp
    aws-cpp-sdk-core/source/utils/StringUtils.cpp
    aws-cpp-sdk-core/source/utils/TempFile.cpp
    aws-cpp-sdk-core/source/utils/threading/Executor.cpp
    aws-cpp-sdk-core/source/utils/threading/ThreadTask.cpp
    aws-cpp-sdk-core/source/utils/UUID.cpp
    aws-cpp-sdk-core/source/utils/xml/XmlSerializer.cpp
    aws-cpp-sdk-core/source/Version.cpp
    aws-cpp-sdk-s3/source/model/AbortIncompleteMultipartUpload.cpp
    aws-cpp-sdk-s3/source/model/AbortMultipartUploadRequest.cpp
    aws-cpp-sdk-s3/source/model/AbortMultipartUploadResult.cpp
    aws-cpp-sdk-s3/source/model/AccelerateConfiguration.cpp
    aws-cpp-sdk-s3/source/model/AccessControlPolicy.cpp
    aws-cpp-sdk-s3/source/model/Bucket.cpp
    aws-cpp-sdk-s3/source/model/BucketAccelerateStatus.cpp
    aws-cpp-sdk-s3/source/model/BucketCannedACL.cpp
    aws-cpp-sdk-s3/source/model/BucketLifecycleConfiguration.cpp
    aws-cpp-sdk-s3/source/model/BucketLocationConstraint.cpp
    aws-cpp-sdk-s3/source/model/BucketLoggingStatus.cpp
    aws-cpp-sdk-s3/source/model/BucketLogsPermission.cpp
    aws-cpp-sdk-s3/source/model/BucketVersioningStatus.cpp
    aws-cpp-sdk-s3/source/model/CloudFunctionConfiguration.cpp
    aws-cpp-sdk-s3/source/model/CommonPrefix.cpp
    aws-cpp-sdk-s3/source/model/CompletedMultipartUpload.cpp
    aws-cpp-sdk-s3/source/model/CompletedPart.cpp
    aws-cpp-sdk-s3/source/model/CompleteMultipartUploadRequest.cpp
    aws-cpp-sdk-s3/source/model/CompleteMultipartUploadResult.cpp
    aws-cpp-sdk-s3/source/model/Condition.cpp
    aws-cpp-sdk-s3/source/model/CopyObjectRequest.cpp
    aws-cpp-sdk-s3/source/model/CopyObjectResult.cpp
    aws-cpp-sdk-s3/source/model/CopyPartResult.cpp
    aws-cpp-sdk-s3/source/model/CORSConfiguration.cpp
    aws-cpp-sdk-s3/source/model/CORSRule.cpp
    aws-cpp-sdk-s3/source/model/CreateBucketConfiguration.cpp
    aws-cpp-sdk-s3/source/model/CreateBucketRequest.cpp
    aws-cpp-sdk-s3/source/model/CreateBucketResult.cpp
    aws-cpp-sdk-s3/source/model/CreateMultipartUploadRequest.cpp
    aws-cpp-sdk-s3/source/model/CreateMultipartUploadResult.cpp
    aws-cpp-sdk-s3/source/model/Delete.cpp
    aws-cpp-sdk-s3/source/model/DeleteBucketCorsRequest.cpp
    aws-cpp-sdk-s3/source/model/DeleteBucketLifecycleRequest.cpp
    aws-cpp-sdk-s3/source/model/DeleteBucketPolicyRequest.cpp
    aws-cpp-sdk-s3/source/model/DeleteBucketReplicationRequest.cpp
    aws-cpp-sdk-s3/source/model/DeleteBucketRequest.cpp
    aws-cpp-sdk-s3/source/model/DeleteBucketTaggingRequest.cpp
    aws-cpp-sdk-s3/source/model/DeleteBucketWebsiteRequest.cpp
    aws-cpp-sdk-s3/source/model/DeletedObject.cpp
    aws-cpp-sdk-s3/source/model/DeleteMarkerEntry.cpp
    aws-cpp-sdk-s3/source/model/DeleteObjectRequest.cpp
    aws-cpp-sdk-s3/source/model/DeleteObjectResult.cpp
    aws-cpp-sdk-s3/source/model/DeleteObjectsRequest.cpp
    aws-cpp-sdk-s3/source/model/DeleteObjectsResult.cpp
    aws-cpp-sdk-s3/source/model/Destination.cpp
    aws-cpp-sdk-s3/source/model/EncodingType.cpp
    aws-cpp-sdk-s3/source/model/Error.cpp
    aws-cpp-sdk-s3/source/model/ErrorDocument.cpp
    aws-cpp-sdk-s3/source/model/Event.cpp
    aws-cpp-sdk-s3/source/model/ExpirationStatus.cpp
    aws-cpp-sdk-s3/source/model/FilterRule.cpp
    aws-cpp-sdk-s3/source/model/FilterRuleName.cpp
    aws-cpp-sdk-s3/source/model/GetBucketAccelerateConfigurationRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketAccelerateConfigurationResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketAclRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketAclResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketCorsRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketCorsResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketLifecycleConfigurationRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketLifecycleConfigurationResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketLocationRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketLocationResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketLoggingRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketLoggingResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketNotificationConfigurationRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketNotificationConfigurationResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketPolicyRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketPolicyResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketReplicationRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketReplicationResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketRequestPaymentRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketRequestPaymentResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketTaggingRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketTaggingResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketVersioningRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketVersioningResult.cpp
    aws-cpp-sdk-s3/source/model/GetBucketWebsiteRequest.cpp
    aws-cpp-sdk-s3/source/model/GetBucketWebsiteResult.cpp
    aws-cpp-sdk-s3/source/model/GetObjectAclRequest.cpp
    aws-cpp-sdk-s3/source/model/GetObjectAclResult.cpp
    aws-cpp-sdk-s3/source/model/GetObjectRequest.cpp
    aws-cpp-sdk-s3/source/model/GetObjectResult.cpp
    aws-cpp-sdk-s3/source/model/GetObjectTorrentRequest.cpp
    aws-cpp-sdk-s3/source/model/GetObjectTorrentResult.cpp
    aws-cpp-sdk-s3/source/model/Grant.cpp
    aws-cpp-sdk-s3/source/model/Grantee.cpp
    aws-cpp-sdk-s3/source/model/HeadBucketRequest.cpp
    aws-cpp-sdk-s3/source/model/HeadObjectRequest.cpp
    aws-cpp-sdk-s3/source/model/HeadObjectResult.cpp
    aws-cpp-sdk-s3/source/model/IndexDocument.cpp
    aws-cpp-sdk-s3/source/model/Initiator.cpp
    aws-cpp-sdk-s3/source/model/LambdaFunctionConfiguration.cpp
    aws-cpp-sdk-s3/source/model/LifecycleConfiguration.cpp
    aws-cpp-sdk-s3/source/model/LifecycleExpiration.cpp
    aws-cpp-sdk-s3/source/model/LifecycleRule.cpp
    aws-cpp-sdk-s3/source/model/ListBucketsResult.cpp
    aws-cpp-sdk-s3/source/model/ListMultipartUploadsRequest.cpp
    aws-cpp-sdk-s3/source/model/ListMultipartUploadsResult.cpp
    aws-cpp-sdk-s3/source/model/ListObjectsRequest.cpp
    aws-cpp-sdk-s3/source/model/ListObjectsResult.cpp
    aws-cpp-sdk-s3/source/model/ListObjectsV2Request.cpp
    aws-cpp-sdk-s3/source/model/ListObjectsV2Result.cpp
    aws-cpp-sdk-s3/source/model/ListObjectVersionsRequest.cpp
    aws-cpp-sdk-s3/source/model/ListObjectVersionsResult.cpp
    aws-cpp-sdk-s3/source/model/ListPartsRequest.cpp
    aws-cpp-sdk-s3/source/model/ListPartsResult.cpp
    aws-cpp-sdk-s3/source/model/LoggingEnabled.cpp
    aws-cpp-sdk-s3/source/model/MetadataDirective.cpp
    aws-cpp-sdk-s3/source/model/MFADelete.cpp
    aws-cpp-sdk-s3/source/model/MFADeleteStatus.cpp
    aws-cpp-sdk-s3/source/model/MultipartUpload.cpp
    aws-cpp-sdk-s3/source/model/NoncurrentVersionExpiration.cpp
    aws-cpp-sdk-s3/source/model/NoncurrentVersionTransition.cpp
    aws-cpp-sdk-s3/source/model/NotificationConfiguration.cpp
    aws-cpp-sdk-s3/source/model/NotificationConfigurationDeprecated.cpp
    aws-cpp-sdk-s3/source/model/NotificationConfigurationFilter.cpp
    aws-cpp-sdk-s3/source/model/Object.cpp
    aws-cpp-sdk-s3/source/model/ObjectCannedACL.cpp
    aws-cpp-sdk-s3/source/model/ObjectIdentifier.cpp
    aws-cpp-sdk-s3/source/model/ObjectStorageClass.cpp
    aws-cpp-sdk-s3/source/model/ObjectVersion.cpp
    aws-cpp-sdk-s3/source/model/ObjectVersionStorageClass.cpp
    aws-cpp-sdk-s3/source/model/Owner.cpp
    aws-cpp-sdk-s3/source/model/Part.cpp
    aws-cpp-sdk-s3/source/model/Payer.cpp
    aws-cpp-sdk-s3/source/model/Permission.cpp
    aws-cpp-sdk-s3/source/model/Protocol.cpp
    aws-cpp-sdk-s3/source/model/PutBucketAccelerateConfigurationRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketAclRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketCorsRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketLifecycleConfigurationRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketLoggingRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketNotificationConfigurationRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketPolicyRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketReplicationRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketRequestPaymentRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketTaggingRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketVersioningRequest.cpp
    aws-cpp-sdk-s3/source/model/PutBucketWebsiteRequest.cpp
    aws-cpp-sdk-s3/source/model/PutObjectAclRequest.cpp
    aws-cpp-sdk-s3/source/model/PutObjectAclResult.cpp
    aws-cpp-sdk-s3/source/model/PutObjectRequest.cpp
    aws-cpp-sdk-s3/source/model/PutObjectResult.cpp
    aws-cpp-sdk-s3/source/model/QueueConfiguration.cpp
    aws-cpp-sdk-s3/source/model/QueueConfigurationDeprecated.cpp
    aws-cpp-sdk-s3/source/model/Redirect.cpp
    aws-cpp-sdk-s3/source/model/RedirectAllRequestsTo.cpp
    aws-cpp-sdk-s3/source/model/ReplicationConfiguration.cpp
    aws-cpp-sdk-s3/source/model/ReplicationRule.cpp
    aws-cpp-sdk-s3/source/model/ReplicationRuleStatus.cpp
    aws-cpp-sdk-s3/source/model/ReplicationStatus.cpp
    aws-cpp-sdk-s3/source/model/RequestCharged.cpp
    aws-cpp-sdk-s3/source/model/RequestPayer.cpp
    aws-cpp-sdk-s3/source/model/RequestPaymentConfiguration.cpp
    aws-cpp-sdk-s3/source/model/RestoreObjectRequest.cpp
    aws-cpp-sdk-s3/source/model/RestoreObjectResult.cpp
    aws-cpp-sdk-s3/source/model/RestoreRequest.cpp
    aws-cpp-sdk-s3/source/model/RoutingRule.cpp
    aws-cpp-sdk-s3/source/model/Rule.cpp
    aws-cpp-sdk-s3/source/model/S3KeyFilter.cpp
    aws-cpp-sdk-s3/source/model/ServerSideEncryption.cpp
    aws-cpp-sdk-s3/source/model/StorageClass.cpp
    aws-cpp-sdk-s3/source/model/Tag.cpp
    aws-cpp-sdk-s3/source/model/Tagging.cpp
    aws-cpp-sdk-s3/source/model/TargetGrant.cpp
    aws-cpp-sdk-s3/source/model/TopicConfiguration.cpp
    aws-cpp-sdk-s3/source/model/TopicConfigurationDeprecated.cpp
    aws-cpp-sdk-s3/source/model/Transition.cpp
    aws-cpp-sdk-s3/source/model/TransitionStorageClass.cpp
    aws-cpp-sdk-s3/source/model/Type.cpp
    aws-cpp-sdk-s3/source/model/UploadPartCopyRequest.cpp
    aws-cpp-sdk-s3/source/model/UploadPartCopyResult.cpp
    aws-cpp-sdk-s3/source/model/UploadPartRequest.cpp
    aws-cpp-sdk-s3/source/model/UploadPartResult.cpp
    aws-cpp-sdk-s3/source/model/VersioningConfiguration.cpp
    aws-cpp-sdk-s3/source/model/WebsiteConfiguration.cpp
    aws-cpp-sdk-s3/source/S3Client.cpp
    aws-cpp-sdk-s3/source/S3Endpoint.cpp
    aws-cpp-sdk-s3/source/S3ErrorMarshaller.cpp
    aws-cpp-sdk-s3/source/S3Errors.cpp)

make_library(aws-sdk-cpp
  OBJECT
  SOURCES
    ${_aws_source_file_list}
  REQUIRES
    curl openssl uuid)

target_optional_compile_flag(aws-sdk-cpp "-Wno-delete-non-virtual-dtor")
target_optional_compile_flag(aws-sdk-cpp "-Wno-return-std-move")

target_compile_definitions(aws-sdk-cpp PRIVATE -DENABLE_CURL_CLIENT)
target_compile_definitions(aws-sdk-cpp PRIVATE -DENABLE_OPENSSL_ENCRYPTION)
target_compile_definitions(aws-sdk-cpp PRIVATE -DJSON_USE_EXCEPTION=0)

# Set up the source file dependencies with the external libraries to make sure that 
# cmake compiles OpenSSL first.  This list was generated by running the following command in this directory and copying and pasting the results here. 
# 
# git grep -o \<openssl/.*\> | sed  's|.*:\<\(.*\)\>|set_source_file_properties(${_aws_source_file_list} PROPERTIES OBJECT_DEPENDS ${CMAKE_SOURCE_DIR}/deps/local/include/\1)|g'

# The following header files are generated by the external dependencies.  This forces the compilation of those dependencies to complete before the above compilation starts.
set(_aws_generated_file_dependencies
openssl/ossl_typ.h
openssl/evp.h
openssl/rand.h
openssl/md5.h
openssl/sha.h
openssl/hmac.h
openssl/err.h
curl/curl.h)

list(TRANSFORM _aws_generated_file_dependencies 
  PREPEND ${CMAKE_SOURCE_DIR}/deps//local/include/)


set_source_files_properties(
  ${_aws_source_file_list} PROPERTIES OBJECT_DEPENDS "${_aws_generated_file_dependencies}")
