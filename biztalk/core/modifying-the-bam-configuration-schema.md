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
# <a name="modifying-the-bam-configuration-schema"></a><span data-ttu-id="451e4-102">修改 BAM 配置架构</span><span class="sxs-lookup"><span data-stu-id="451e4-102">Modifying the BAM Configuration Schema</span></span>
<span data-ttu-id="451e4-103">配置向导将自动创建此配置文件。</span><span class="sxs-lookup"><span data-stu-id="451e4-103">The Configuration Wizard creates this configuration file automatically.</span></span> <span data-ttu-id="451e4-104">如果在完成部署后更改了服务器名称或其他配置信息，必须手动修改此文件。</span><span class="sxs-lookup"><span data-stu-id="451e4-104">You must modify this file manually if you change your server names or other configuration information after you complete the deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="451e4-105">若要执行他们所做的更改 BAM 配置文件中，管理员必须取消部署当前 BAM 配置，然后部署已更新的 BAMConfiguration.xml。</span><span class="sxs-lookup"><span data-stu-id="451e4-105">To enact the changes they make in the BAM configuration file, administrators must undeploy the current BAM configuration, and then deploy the updated BAMConfiguration.xml.</span></span>  
  
 <span data-ttu-id="451e4-106">有关取消部署 BAM 定义的信息，请参阅[取消部署 BAM 定义](../core/how-to-remove-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="451e4-106">For information about undeploying a BAM definition, see [Undeploying BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span> <span data-ttu-id="451e4-107">有关部署 BAM 定义的信息，请参阅[部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="451e4-107">For information about deploying a BAM definition, see [Deploying BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="451e4-108">下面是用于 BAMConfiguration.xml 文件的架构：</span><span class="sxs-lookup"><span data-stu-id="451e4-108">The following is the schema used for the BAMConfiguration.xml file:</span></span>  
  
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
  
 <span data-ttu-id="451e4-109">下面的示例是符合 BAM 配置架构的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="451e4-109">The following example is an XML file that conforms to the BAM configuration schema.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="451e4-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="451e4-110">See Also</span></span>  
 <span data-ttu-id="451e4-111">[BAM 配置架构](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="451e4-111">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 <span data-ttu-id="451e4-112">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="451e4-112">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="451e4-113">业务活动监视 (BAM)</span><span class="sxs-lookup"><span data-stu-id="451e4-113">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)