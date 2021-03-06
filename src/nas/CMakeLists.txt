set(ASN1RELDIR r10.5)
include_directories(${SRC_TOP_DIR}/common)
include_directories(${SRC_TOP_DIR}/common/itti)
include_directories(${CMAKE_BINARY_DIR}/s1ap/${ASN1RELDIR})
include_directories(${SRC_TOP_DIR}/mme_app)
include_directories(${SRC_TOP_DIR}/secu)
include_directories(${SRC_TOP_DIR}/sgw)
include_directories(${SRC_TOP_DIR}/s6a)
include_directories(${SRC_TOP_DIR}/utils)
include_directories(${SRC_TOP_DIR}/utils/bstr)
include_directories(${SRC_TOP_DIR}/utils/hashtable)
include_directories(${SRC_TOP_DIR}/utils/msc)
include_directories(${SRC_TOP_DIR}/mme)

# TODO (amar) fix include leak
include_directories("${SRC_TOP_DIR}/nas")
include_directories("${SRC_TOP_DIR}/nas/emm")
include_directories("${SRC_TOP_DIR}/nas/emm/msg")
include_directories("${SRC_TOP_DIR}/nas/emm/sap")
include_directories("${SRC_TOP_DIR}/nas/api")
include_directories("${SRC_TOP_DIR}/nas/ies")
include_directories("${SRC_TOP_DIR}/nas/util")
include_directories("${SRC_TOP_DIR}/nas/esm")
include_directories("${SRC_TOP_DIR}/nas/esm/msg")
include_directories("${SRC_TOP_DIR}/nas/api/network")
include_directories("${SRC_TOP_DIR}/nas/api/mme")
include_directories("${SRC_TOP_DIR}/s1ap/messages/asn1/${ASN1RELDIR}")
include_directories("${SRC_TOP_DIR}/s1ap")

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/api/network)
set(libnas_api_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/api/network/nas_message.c
    )

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/api/mme)
set(libnas_mme_api_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/api/mme/mme_api.c
    )

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/emm/msg)
set(libnas_emm_msg_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/AttachAccept.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/AttachComplete.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/AttachReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/AttachRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/AuthenticationFailure.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/AuthenticationReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/AuthenticationRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/AuthenticationResponse.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/CsServiceNotification.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/DetachAccept.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/DetachRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/DownlinkNasTransport.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/EmmInformation.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/emm_msg.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/EmmStatus.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/ExtendedServiceRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/GutiReallocationCommand.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/GutiReallocationComplete.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/IdentityRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/IdentityResponse.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/SecurityModeCommand.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/SecurityModeComplete.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/SecurityModeReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/ServiceReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/ServiceRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/TrackingAreaUpdateAccept.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/TrackingAreaUpdateComplete.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/TrackingAreaUpdateReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/TrackingAreaUpdateRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/msg/UplinkNasTransport.c
    )

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/esm/msg)
set(libnas_esm_msg_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/ActivateDedicatedEpsBearerContextAccept.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/ActivateDedicatedEpsBearerContextReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/ActivateDedicatedEpsBearerContextRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/ActivateDefaultEpsBearerContextAccept.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/ActivateDefaultEpsBearerContextReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/ActivateDefaultEpsBearerContextRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/BearerResourceAllocationReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/BearerResourceAllocationRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/BearerResourceModificationReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/BearerResourceModificationRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/DeactivateEpsBearerContextAccept.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/DeactivateEpsBearerContextRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/EsmInformationRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/EsmInformationResponse.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/esm_msg.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/EsmStatus.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/ModifyEpsBearerContextAccept.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/ModifyEpsBearerContextReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/ModifyEpsBearerContextRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/PdnConnectivityReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/PdnConnectivityRequest.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/PdnDisconnectReject.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/msg/PdnDisconnectRequest.c
    )

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/ies)
set(libnas_ies_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/AdditionalUpdateResult.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/AdditionalUpdateType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/ApnAggregateMaximumBitRate.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/Cli.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/CsfbResponse.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/DetachType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EmmCause.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EpsAttachResult.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EpsAttachType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EpsBearerContextStatus.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EpsMobileIdentity.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EpsNetworkFeatureSupport.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EpsQualityOfService.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EpsUpdateResult.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EpsUpdateType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EsmCause.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EsmInformationTransferFlag.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/EsmMessageContainer.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/GutiType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/KsiAndSequenceNumber.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/LcsClientIdentity.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/LcsIndicator.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/LinkedEpsBearerIdentity.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/MessageType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/NasKeySetIdentifier.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/NasMessageContainer.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/NasRequestType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/NasSecurityAlgorithms.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/Nonce.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/PagingIdentity.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/PdnAddress.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/PdnType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/RadioPriority.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/SecurityHeaderType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/ServiceType.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/ShortMac.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/SsCode.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/TrackingAreaIdentity.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/TrackingAreaIdentityList.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/UeAdditionalSecurityCapability.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/UeNetworkCapability.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/UeRadioCapabilityInformationUpdateNeeded.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ies/UeSecurityCapability.c
    )

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/util)
set (libnas_utils_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/util/nas_timer.c
    )

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/api/mme)
set(libnas_mme_api_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/api/mme/mme_api.c
    )

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/emm)
set(libnas_mme_emm_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/Attach.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/Authentication.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/Detach.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/emm_data_ctx.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/emm_main.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/EmmStatusHdl.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/Identification.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/LowerLayer.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/nas_emm_proc.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/nas_emm_procedures.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/nas_emm_task.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/SecurityModeControl.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/ServiceRequestHdl.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/TrackingAreaUpdate.c
    )

if(${MOBILITY_REPO})
  include_directories ("${MOBILITY_REPO_SRC}/src/nas/emm")
  set(libnas_mme_emm_OBJS
    ${libnas_mme_emm_OBJS}
    ${MOBILITY_REPO_SRC}/src/nas/emm/TrackingAreaUpdateMobility.c
  )
else (${MOBILITY_REPO})
  set(libnas_mme_emm_OBJS
    ${libnas_mme_emm_OBJS}
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/TrackingAreaUpdateMobility.c
  )
endif ()


include_directories(${CMAKE_CURRENT_SOURCE_DIR}/emm/sap)
set(libnas_mme_emm_sap_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/emm_as.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/emm_cn.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/EmmCommonProcedureInitiated.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/EmmDeregistered.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/EmmDeregisteredInitiated.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/emm_esm.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/emm_fsm.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/emm_recv.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/emm_reg.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/EmmRegistered.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/emm_sap.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/sap/emm_send.c
    )

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/esm)
set (libnas_mme_esm_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/BearerResourceAllocation.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/BearerResourceModification.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/DedicatedEpsBearerContextActivation.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/DefaultEpsBearerContextActivation.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/EpsBearerContextDeactivation.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/EpsBearerContextModification.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/esm_data_context.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/esm_ebr.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/esm_ebr_context.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/esm_information.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/esm_ip.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/esm_main.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/esm_pt.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/EsmStatusHdl.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/nas_esm_proc.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/nas_esm_procedures.c
    ${CMAKE_CURRENT_SOURCE_DIR}/emm/nas_esm_task.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/PdnConnectivity.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/PdnDisconnect.c
    )

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/esm/sap)
set(libnas_mme_esm_sap_OBJS
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/sap/esm_recv.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/sap/esm_send.c
    ${CMAKE_CURRENT_SOURCE_DIR}/esm/sap/esm_sap.c
    )

add_library(LIB_NAS_MME
    nas_itti_messaging.c
    nas_network.c
    ${libnas_api_OBJS}
    ${libnas_mme_api_OBJS}
    ${libnas_emm_msg_OBJS}
    ${libnas_esm_msg_OBJS}
    ${libnas_ies_OBJS}
    ${libnas_utils_OBJS}
    ${libnas_mme_emm_OBJS}
    ${libnas_mme_emm_sap_OBJS}
    ${libnas_mme_esm_OBJS}
    ${libnas_mme_esm_sap_OBJS}
    )
