#
# UK Crown Copyright (c) 2016. All Rights Reserved
#
find_package(Boost REQUIRED)


set(GENSRC
    src/BS_AssociationTerminator.cc
    src/BS_Attribute.cc
    src/BS_AttributeAccessMethod.cc
    src/BS_BuildSet.cc
    src/BS_ClassOfDomainVersionInBuildSet.cc
    src/BS_CounterpartAssociation.cc
    src/BS_CounterpartGeneralisation.cc
    src/BS_DomainVersionInBuildSet.cc
    src/BS_DomainVersionInitialisationSegment.cc
    src/BS_GenericAttributeAccessMapping.cc
    src/BS_GenericClassInCounterpartGeneralisation.cc
    src/BS_InitialisationSequence.cc
    src/BS_MappedOperationProvidedByGenericClass.cc
    src/BS_MappedOperationProvidedBySpecificClass.cc
    src/BS_NonCounterpartTerminator.cc
    src/BS_OperationProvidedBySpecificClass.cc
    src/BS_PostExecutionMappingForOperationOfSpecificClass.cc
    src/BS_PostExecutionMappingForStateActionOfSpecificClass.cc
    src/BS_PreExecutionMappingForOperationOfSpecificClass.cc
    src/BS_PreExecutionMappingForStateActionOfSpecificClass.cc
    src/BS_SignalDefinedForSpecificClass.cc
    src/BS_SignalDispatchMappingForSpecificClass.cc
    src/BS_SpecialisationTerminator.cc
    src/BS_SpecialisationTerminatorOperationRequirement.cc
    src/BS_SpecialisationTerminatorOperationRequirementMapping.cc
    src/BS_SpecificAttributeAccessMapping.cc
    src/BS_SpecificClassInCounterpartGeneralisation.cc
    src/BS_StateActionOfSpecificClass.cc
    src/BS_SupplementaryCodeBlock.cc
    src/BS_TerminatorOperationBridge.cc
    src/BS_TerminatorOperationInputParameter.cc
    src/BS_TerminatorOperationOutputParameter.cc
    src/BS_TerminatorOperationParameter.cc
    src/BS_TerminatorSignalBridge.cc
    src/BS_TerminatorSignalParameter.cc
    src/ORG_BuildSet.cc
    src/ORG_Database.cc
    src/ORG_Domain.cc
    src/ORG_DomainVersion.cc
    src/ORG_Group.cc
    src/ORG_Package.cc
    src/ORG_PackageContainerDomainVersion.cc
    src/ORG_PackageVersion.cc
    src/ORG_Project.cc
    src/ORG_ProjectVersion.cc
    src/ORG_StandardDomainVersion.cc
    src/ORG_User.cc
    src/TAGS_Tag.cc
    src/TAGS_TagAttachment.cc
    src/TAGS_TagEnumeration.cc
    src/TAGS_TaggedItem.cc
    src/TAGS_TagGroup.cc
    src/TAGS_TagOwner.cc
    src/XUML_AnalysisArea.cc
    src/XUML_AssignerEffect.cc
    src/XUML_AssignerSignal.cc
    src/XUML_AssignerSPC.cc
    src/XUML_AssignerState.cc
    src/XUML_AssignerStateModel.cc
    src/XUML_AssociationClass.cc
    src/XUML_AssociationTerminator.cc
    src/XUML_AssociationTerminatorOperation.cc
    src/XUML_Attribute.cc
    src/XUML_AttributeReference.cc
    src/XUML_Class.cc
    src/XUML_ClassOperation.cc
    src/XUML_ConstrainedDateType.cc
    src/XUML_ConstrainedIntegerType.cc
    src/XUML_ConstrainedRealType.cc
    src/XUML_ConstrainedTextType.cc
    src/XUML_ConstrainedTimeOfDayType.cc
    src/XUML_DataStructureMember.cc
    src/XUML_DataStructureType.cc
    src/XUML_DataType.cc
    src/XUML_DeferredOperation.cc
    src/XUML_DeferredOperationImplementation.cc
    src/XUML_DeferredType.cc
    src/XUML_DerivedAssociation.cc
    src/XUML_DomainOperation.cc
    src/XUML_Effect.cc
    src/XUML_EnumerationElement.cc
    src/XUML_EnumerationType.cc
    src/XUML_ExistingInstanceState.cc
    src/XUML_FormalisedAssociation.cc
    src/XUML_FurtherOperationDeferral.cc
    src/XUML_Generalisation.cc
    src/XUML_Identifier.cc
    src/XUML_InitialisationSegment.cc
    src/XUML_InitialisationSequence.cc
    src/XUML_InitialisationSequenceComponent.cc
    src/XUML_InstanceHandleType.cc
    src/XUML_InstanceSPC.cc
    src/XUML_InstanceState.cc
    src/XUML_InstanceStateModel.cc
    src/XUML_NonAssociationClass.cc
    src/XUML_NonCounterpartTerminator.cc
    src/XUML_NonCounterpartTerminatorOperation.cc
    src/XUML_NonexistentState.cc
    src/XUML_NonReferentialAttribute.cc
    src/XUML_Operation.cc
    src/XUML_OperationParameter.cc
    src/XUML_PolymorphicOperation.cc
    src/XUML_ProvidedDataType.cc
    src/XUML_ReferentialAttribute.cc
    src/XUML_ReferentialIdentifier.cc
    src/XUML_Signal.cc
    src/XUML_SignalParameter.cc
    src/XUML_SignalProducerConsumer.cc
    src/XUML_SignalTransmission.cc
    src/XUML_SignalUsage.cc
    src/XUML_SpecialisationTerminator.cc
    src/XUML_SpecialisationTerminatorOperation.cc
    src/XUML_SubclassParticipation.cc
    src/XUML_SupplementaryCodeBlock.cc
    src/XUML_SupplementarySignalParameterCarriedByUMLSignal.cc
    src/XUML_TerminatorSignal.cc
    src/XUML_TestMethod.cc
    src/XUML_TestMethodSet.cc
    src/XUML_UMLAssociation.cc
    src/XUML_UMLSignal.cc
    src/XUML_UserDefinedDataType.cc
)

add_custom_command (
  OUTPUT ${GENSRC}
  COMMAND APIGen ${CMAKE_CURRENT_BINARY_DIR} BS ORG XUML TAGS
  DEPENDS APIGen
          gen-src/counterparts.txt
          gen-src/creates.txt
          gen-src/deletes.txt
          gen-src/lookups.txt
          gen-src/BS.obj
          gen-src/BS.rel
          gen-src/BS.sub
          gen-src/ORG_Database.class_extras.hh
          gen-src/ORG_Database.extras.cc
          gen-src/ORG_Domain.class_extras.hh
          gen-src/ORG_Domain.extras.cc
          gen-src/ORG_DomainVersion.class_extras.hh
          gen-src/ORG_DomainVersion.extras.cc
          gen-src/ORG.obj
          gen-src/ORG_Project.class_extras.hh
          gen-src/ORG_Project.extras.cc
          gen-src/ORG_ProjectVersion.class_extras.hh
          gen-src/ORG_ProjectVersion.extras.cc
          gen-src/ORG.rel
          gen-src/ORG.sub
          gen-src/TAGS.obj
          gen-src/TAGS.rel
          gen-src/TAGS.sub
          gen-src/TAGS_Tag.class_extras.hh
          gen-src/TAGS_Tag.extras.cc
          gen-src/TAGS_TaggedItem.class_extras.hh
          gen-src/TAGS_TaggedItem.extras.cc
          gen-src/XUML_NonCounterpartTerminatorOperation.class_extras.hh
          gen-src/XUML_NonCounterpartTerminatorOperation.extras.cc
          gen-src/XUML.obj
          gen-src/XUML_OperationParameter.class_extras.hh
          gen-src/XUML_OperationParameter.extras.cc
          gen-src/XUML.rel
          gen-src/XUML.sub
          gen-src/XUML_UserDefinedDataType.class_extras.hh
          gen-src/XUML_UserDefinedDataType.extras.cc

  WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/gen-src
  )
  
add_custom_target ( generate-api ALL DEPENDS ${GENSRC} )

add_library ( 
  iUMLAPI SHARED
    src/Entity.cc
    src/Session.cc
    src/Utils.cc
    src/iUMLAPI.cc 
    ${GENSRC}
  )

add_dependencies ( iUMLAPI generate-api )

target_link_libraries (
  iUMLAPI
    PRIVATE
      -L${UML_ROOT}/lib
      -L${UML_ROOT}/api/lib
        api
        ABGUI 
        ABSTD 
        C 
        DBG 
        DBI 
        DEASEL 
        EASEL 
        FRAMEWORKS 
        LOGIC 
        MI 
        OM 
        OOA 
        PRINT 
        R3 
        SE 
        TBK 
        TBK1 
        TEBAS 
        TM
  )

target_include_directories (
  iUMLAPI
    SYSTEM PUBLIC 
      ${UML_ROOT}/api/include 
      ${UML_ROOT}/include
      ${Boost_INCLUDE_DIRS}
  )

target_include_directories (
  iUMLAPI
    PUBLIC
      $<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}/include>
      $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
)

install ( 
  TARGETS
          iUMLAPI 
  EXPORT  iUML
  LIBRARY DESTINATION ${INSTALL_LIB_DIR}
)

install (
  DIRECTORY   include/
  DESTINATION ${INSTALL_INCLUDE_DIR}
)

install (
  DIRECTORY   ${CMAKE_CURRENT_BINARY_DIR}/include/
  DESTINATION ${INSTALL_INCLUDE_DIR}
)

