---
title: "使用 BizTalk ESB 工具包实用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2dc05ac-831a-44e1-bd44-e41398552ab1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db4a8ef2def05e0b77d272463d7a79f937623b1a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-biztalk-esb-toolkit-utilities"></a><span data-ttu-id="e0719-102">使用 BizTalk ESB 工具包实用程序</span><span class="sxs-lookup"><span data-stu-id="e0719-102">Using the BizTalk ESB Toolkit Utilities</span></span>
<span data-ttu-id="e0719-103">本部分介绍各种实用程序作为的一部分包括[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e0719-103">This section describes various utilities included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="e0719-104">**ESB 路线导入实用程序**</span><span class="sxs-lookup"><span data-stu-id="e0719-104">**ESB Itinerary Import Utility**</span></span>  
  
 <span data-ttu-id="e0719-105">此实用程序位于 \bin 目录的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和名为 EsbImportUtil.exe。</span><span class="sxs-lookup"><span data-stu-id="e0719-105">This utility is located under the \bin directory of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and is named EsbImportUtil.exe.</span></span> <span data-ttu-id="e0719-106">此实用工具可以用于发布或部署到 ESBItineraryDB 数据库路线 XML。</span><span class="sxs-lookup"><span data-stu-id="e0719-106">This utility can be used to publish or deploy the itinerary XML into the ESBItineraryDB database.</span></span>  
  
 <span data-ttu-id="e0719-107">实用程序的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0719-107">The syntax for the utility is as follows:</span></span>  
  
```  
>EsbImportUtil <Parameter1> <Value> <parameter2> <Value>...  
```  
  
 <span data-ttu-id="e0719-108">它可以接受的各种参数如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0719-108">The various parameters it can accept are the following:</span></span>  
  
 <span data-ttu-id="e0719-109">/？:\<显示帮助的参数\></span><span class="sxs-lookup"><span data-stu-id="e0719-109">/?: \<Show the parameters help\></span></span>  
  
 <span data-ttu-id="e0719-110">/f:\<路线 xml 文件路径\></span><span class="sxs-lookup"><span data-stu-id="e0719-110">/f: \<Itinerary xml file path\></span></span>  
  
 <span data-ttu-id="e0719-111">无\<发布 &#124; 部署\></span><span class="sxs-lookup"><span data-stu-id="e0719-111">/c: \<published &#124; deployed\></span></span>  
  
 <span data-ttu-id="e0719-112">/n:\<默认路线名称\></span><span class="sxs-lookup"><span data-stu-id="e0719-112">/n: \<Default Itinerary name\></span></span>  
  
 <span data-ttu-id="e0719-113">/v:\<默认路线版本 （格式 major.minor）\></span><span class="sxs-lookup"><span data-stu-id="e0719-113">/v: \<Default Itinerary version (format 'major.minor')\></span></span>  
  
 <span data-ttu-id="e0719-114">/o:\<静默覆盖\></span><span class="sxs-lookup"><span data-stu-id="e0719-114">/o: \<Silent overwrite\></span></span>  
  
 <span data-ttu-id="e0719-115">以下是如何使用此实用工具的示例。</span><span class="sxs-lookup"><span data-stu-id="e0719-115">The following are examples of how to use this utility.</span></span>  
  
 <span data-ttu-id="e0719-116">将发布到路线数据库：</span><span class="sxs-lookup"><span data-stu-id="e0719-116">To publish to the Itinerary database:</span></span>  
  
```  
>EsbImportUtil /f:myitinerary.xml /c:published  
```  
  
 <span data-ttu-id="e0719-117">若要部署到路线数据库：</span><span class="sxs-lookup"><span data-stu-id="e0719-117">To deploy to the Itinerary database:</span></span>  
  
```  
>EsbImportUtil  /f:myitinerary.xml /c:deployed  
```  
  
 <span data-ttu-id="e0719-118">**SSO 配置保留实用程序**</span><span class="sxs-lookup"><span data-stu-id="e0719-118">**SSO Configuration Persist Utility**</span></span>  
  
 <span data-ttu-id="e0719-119">此实用程序位于 \bin 目录的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和名为 Microsoft.Practices.ESB.PersistConfigurationTool.exe。</span><span class="sxs-lookup"><span data-stu-id="e0719-119">This utility is located under the \bin directory of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and is named Microsoft.Practices.ESB.PersistConfigurationTool.exe.</span></span> <span data-ttu-id="e0719-120">此实用工具可以用于持久保存到 BizTalk SSO 数据库的 ESB 配置信息。</span><span class="sxs-lookup"><span data-stu-id="e0719-120">This utility can be used to persist the ESB configuration information into the BizTalk SSO database.</span></span> <span data-ttu-id="e0719-121">这还可查看配置信息和从 SSO 数据库中删除的配置信息。</span><span class="sxs-lookup"><span data-stu-id="e0719-121">This can also be used to view configuration information and remove the configuration information from the SSO database.</span></span>  
  
 <span data-ttu-id="e0719-122">实用程序的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0719-122">The syntax for the utility is as follows:</span></span>  
  
 <span data-ttu-id="e0719-123">**若要添加一个配置节：**</span><span class="sxs-lookup"><span data-stu-id="e0719-123">**To add a configuration section:**</span></span>  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /P /F:app.config /S:SectionName /A:ApplicationName  
```  
  
> [!NOTE]
>  <span data-ttu-id="e0719-124">如果未提供 /S，将添加以下各节： connectionStrings，esb、 esb.resolver 和 cachingConfiguration。</span><span class="sxs-lookup"><span data-stu-id="e0719-124">If /S is not provided, the following sections will be added: connectionStrings, esb, esb.resolver and cachingConfiguration.</span></span>  
  
 <span data-ttu-id="e0719-125">**若要删除节：**</span><span class="sxs-lookup"><span data-stu-id="e0719-125">**To remove a section:**</span></span>  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /R /S:SectionName  
```  
  
 <span data-ttu-id="e0719-126">若要查看现有的内容，请将应用程序和部分开关用于 /V 开关。</span><span class="sxs-lookup"><span data-stu-id="e0719-126">To view an existing section, use the application and section switches with the /V switch.</span></span>  
  
 <span data-ttu-id="e0719-127">若要设置管理员组名称，请使用 AG:AdminGroupName 交换机。</span><span class="sxs-lookup"><span data-stu-id="e0719-127">To set the administrator group name, use the AG:AdminGroupName switch.</span></span>  
  
 <span data-ttu-id="e0719-128">若要设置的用户组名称，使用 UG:UserGroupName 开关。</span><span class="sxs-lookup"><span data-stu-id="e0719-128">To set the user group name, use the UG:UserGroupName switch.</span></span>