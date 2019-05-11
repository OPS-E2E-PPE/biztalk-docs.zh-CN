---
title: 修改 BAM 配置架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuration schema [BAM]
- managing [BAM], configuration schema
- BAMConfiguration.xml file
ms.assetid: 8901fb05-1519-4033-8489-67a9b745ed43
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18537eca346eef03676978a0e80c31e2daed9ba1
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527591"
---
# <a name="modifying-the-bam-configuration-schema"></a>修改 BAM 配置架构
配置向导将自动创建此配置文件。 如果在完成部署后更改了服务器名称或其他配置信息，必须手动修改此文件。  
  
> [!NOTE]
>  若要执行他们所做的更改 BAM 配置文件中，管理员必须取消部署当前 BAM 配置，然后部署已更新的 BAMConfiguration.xml。  
  
 有关取消部署 BAM 定义的信息，请参阅[取消部署 BAM 定义](../core/how-to-remove-bam-definitions.md)。 有关部署 BAM 定义的信息，请参阅[部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。  
  
 下面是用于 BAMConfiguration.xml 文件的架构：  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="urn:schemas-microsoft.com:BAM" targetNamespace="urn:schemas-microsoft.com:BAM" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
     <xs:element name="BAMConfiguration">  
          <xs:complexType>  
               <xs:sequence>  
                    <xs:element name="DeploymentUnit" maxOccurs="unbounded" type="DeploymentUnit" />  
               </xs:sequence>  
          </xs:complexType>  
     </xs:element>  
     <xs:complexType name="DeploymentUnit">  
          <xs:sequence>  
               <xs:element name="Property" maxOccurs="unbounded" type="Property" />  
          </xs:sequence>  
          <xs:attribute name="Name" type="xs:string" />  
     </xs:complexType>  
     <xs:complexType name="Property">  
          <xs:simpleContent>  
               <xs:extension base='xs:string'>  
                    <xs:attribute name='Name' type='xs:NCName' />  
               </xs:extension>  
          </xs:simpleContent>  
     </xs:complexType>  
</xs:schema>  
```  
  
 下面的示例是符合 BAM 配置架构的 XML 文件。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<BAM:BAMConfiguration xmlns:BAM='urn:schemas-microsoft.com:BAM' xmlns:xsi='http://www.w3.org/2001/XMLSchema-instance'>  
     <DeploymentUnit Name="PrimaryImportDatabase">  
          <Property Name="ServerName">.</Property>  
          <Property Name="DatabaseName">BAMPrimaryImport</Property>  
          <Property Name="RTAWindow">60</Property>  
          <Property Name="RTATimeSlice">5</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="StarSchemaDatabase">  
          <Property Name="ServerName">.</Property>  
          <Property Name="DatabaseName">BAMStarSchema</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="AnalysisDatabase">  
          <Property Name="ServerName">localhost</Property>  
          <Property Name="DatabaseName">BAMAnalysis</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="ArchivingDatabase">  
          <Property Name="ServerName">.</Property>  
          <Property Name="DatabaseName">BAMArchiving</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="CubeUpdateDTS">  
          <Property Name="ConnectionTimeOut">15</Property>  
          <Property Name="UseEncryption">1</Property>  
          <Property Name="OwnerPassword">myOwnerPassword</Property>  
          <Property Name="UserPassword">myUserPassword</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="DataMaintenanceDTS">  
          <Property Name="ConnectionTimeOut">15</Property>  
          <Property Name="UseEncryption">1</Property>  
          <Property Name="OwnerPassword">myOwnerPassword</Property>  
          <Property Name="UserPassword">myUserPassword</Property>       
     </DeploymentUnit>  
</BAM:BAMConfiguration>  
```  
  
## <a name="see-also"></a>请参阅  
 [BAM 配置架构](../core/bam-configuration-schema.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [业务活动监视 (BAM)](../core/business-activity-monitoring-bam.md)