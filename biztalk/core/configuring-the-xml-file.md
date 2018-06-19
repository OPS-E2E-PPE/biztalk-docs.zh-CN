---
title: 配置 XML 文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52851901-8374-412f-9c29-83845d8d4861
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d791de9b6fe90ebb850874026e8d52e49732f32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233821"
---
# <a name="configuring-the-xml-file"></a><span data-ttu-id="6213d-102">配置 XML 文件</span><span class="sxs-lookup"><span data-stu-id="6213d-102">Configuring the XML File</span></span>
<span data-ttu-id="6213d-103">在安装企业单一登录 (SSO) 时，会在 Extensions 目录下安装一个名为 ENTSSO.xml 的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="6213d-103">When you install Enterprise Single Sign-On (SSO), an XML file named ENTSSO.xml is installed in your Extensions directory.</span></span> <span data-ttu-id="6213d-104">通过编辑该文件，可定义 ENTSSO 管理代理 (MA) 所有实例的配置。</span><span class="sxs-lookup"><span data-stu-id="6213d-104">By editing the file, you define the configuration for all instances of the ENTSSO Management Agent (MA).</span></span>  
  
 <span data-ttu-id="6213d-105">该文件与以下内容类似：</span><span class="sxs-lookup"><span data-stu-id="6213d-105">The file is similar to the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<sso>  
  
  <SourceMA name="RACFMA1" objectType="person" attribute="uid"/>  
  <SourceMA name="ACF2" objectType="person" attribute="uid"/>  
  
  <ENTSSOMA name ="ENTSSOMA1" adma="ADMA1" deleteAll="true">  
    <Application name="AppForRACF1A" sourceMA="RACFMA1" create="true" delete="true"/>  
    <Application name="AppForRACF1B" sourceMA="RACFMA1" create="true" delete="false"/>  
  </ENTSSOMA>  
  
  <ENTSSOMA name ="ENTSSOMA2" adma="ADMA1" deleteAll="true">  
    <Application name="AppForACF2" sourceMA="ACF2"/>  
  </ENTSSOMA>  
  
</sso>  
```  
  
## <a name="xml-elements-and-attributes"></a><span data-ttu-id="6213d-106">XML 元素和属性</span><span class="sxs-lookup"><span data-stu-id="6213d-106">XML Elements and Attributes</span></span>  
 <span data-ttu-id="6213d-107">下面的列表介绍了您在该 XML 文件中定义的元素和属性。</span><span class="sxs-lookup"><span data-stu-id="6213d-107">The following list describes the elements and attributes that you define in the XML file.</span></span> <span data-ttu-id="6213d-108">请注意，此文件中所有元素和属性的名称都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="6213d-108">Note that all element and attribute names in this file are case sensitive.</span></span>  
  
 <span data-ttu-id="6213d-109">**元素： ENTSSO** -定义单个 ENTSSO MA 实例的配置。</span><span class="sxs-lookup"><span data-stu-id="6213d-109">**Element: ENTSSO** - Defines the configuration of a single ENTSSO MA instance.</span></span> <span data-ttu-id="6213d-110">允许使用多个 ENTSSO 元素。</span><span class="sxs-lookup"><span data-stu-id="6213d-110">Multiple ENTSSO elements are allowed.</span></span>  
  
 <span data-ttu-id="6213d-111">**属性： 命名**-定义 ENTSSO 管理代理的实例名称，并且必须匹配 ENTSSO 管理代理实例中 Microsoft 标识集成服务器 （miis 进行） 的名称。</span><span class="sxs-lookup"><span data-stu-id="6213d-111">**Attribute: name** - Defines the instance name of the ENTSSO Management Agent, and must match the name of the ENTSSO Management Agent instance in Microsoft Identity Integration Server (MIIS).</span></span>  
  
 <span data-ttu-id="6213d-112">**属性： adma** -定义此 ENTSSO 管理代理实例将使用 Active Directory 管理代理的实例名称。</span><span class="sxs-lookup"><span data-stu-id="6213d-112">**Attribute: adma** - Defines the instance name of the Active Directory Management Agent that will be used by this ENTSSO Management Agent instance.</span></span> <span data-ttu-id="6213d-113">Active Directory 管理代理为映射提供了 Windows 域名和 Windows 用户名。</span><span class="sxs-lookup"><span data-stu-id="6213d-113">The Active Directory Management Agent provides the Windows domain name and Windows user name for the mapping.</span></span> <span data-ttu-id="6213d-114">此 Active Directory 管理代理实例的名称必须与 MIIS 中的 Active Directory 管理代理实例的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="6213d-114">This Active Directory Management Agent instance name must match the name of an Active Directory Management Agent instance in MIIS.</span></span>  
  
 <span data-ttu-id="6213d-115">**属性： deleteAll** -可选的; 默认值是`true`。</span><span class="sxs-lookup"><span data-stu-id="6213d-115">**Attribute: deleteAll** - Optional; default is `true`.</span></span> <span data-ttu-id="6213d-116">如果此值设置为`true`，并删除 Windows 标识，将从所有 ENTSSO 应用程序中删除具有该 Windows 标识的所有映射。</span><span class="sxs-lookup"><span data-stu-id="6213d-116">If this is set to `true`, and a Windows identity is deleted, all mappings with that Windows identity are deleted from all ENTSSO applications.</span></span>  
  
 <span data-ttu-id="6213d-117">**元素： 应用程序**-定义 SSO 关联应用程序和外部管理代理之间的关系。</span><span class="sxs-lookup"><span data-stu-id="6213d-117">**Element: Application** - Defines the relationship between an SSO affiliate application and an external Management Agent.</span></span> <span data-ttu-id="6213d-118">多个`Application`允许的元素。</span><span class="sxs-lookup"><span data-stu-id="6213d-118">Multiple `Application` elements are allowed.</span></span>  
  
 <span data-ttu-id="6213d-119">**属性： 命名**-定义 SSO 关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="6213d-119">**Attribute: name** - Defines the name of the SSO affiliate application.</span></span> <span data-ttu-id="6213d-120">此应用程序必须已存在于 ENTSSO 系统中。</span><span class="sxs-lookup"><span data-stu-id="6213d-120">This application must already exist within the ENTSSO system.</span></span>  
  
 <span data-ttu-id="6213d-121">**属性： sourceMA** -定义源 （外部） 的实例名称将用于提供此应用程序的映射中的外部用户 Id 的管理代理。</span><span class="sxs-lookup"><span data-stu-id="6213d-121">**Attribute: sourceMA** - Defines the instance name for the source (external) Management Agent that will be used to provide the external UserId in the mapping for this application.</span></span> <span data-ttu-id="6213d-122">此外部管理代理实例的名称必须与 MIIS 中外部 MA 实例的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="6213d-122">This external Management Agent instance name must match the name of an external MA instance in MIIS.</span></span>  
  
 <span data-ttu-id="6213d-123">**属性： 创建**-可选的; 默认值是`true`。</span><span class="sxs-lookup"><span data-stu-id="6213d-123">**Attribute: create** - Optional; default is `true`.</span></span> <span data-ttu-id="6213d-124">定义是否应为此应用程序创建映射。</span><span class="sxs-lookup"><span data-stu-id="6213d-124">Defines whether mappings should be created for this application.</span></span>  
  
 <span data-ttu-id="6213d-125">**属性： 删除**-可选的; 默认值是`true`。</span><span class="sxs-lookup"><span data-stu-id="6213d-125">**Attribute: delete** - Optional; default is `true`.</span></span> <span data-ttu-id="6213d-126">定义是否应为此应用程序删除映射。</span><span class="sxs-lookup"><span data-stu-id="6213d-126">Defines whether mappings should be deleted for this application.</span></span>  
  
 <span data-ttu-id="6213d-127">**元素： SourceMA** -可选。</span><span class="sxs-lookup"><span data-stu-id="6213d-127">**Element: SourceMA** - Optional.</span></span> <span data-ttu-id="6213d-128">标识特定源（外部）管理代理实例的对象类型和属性名称。</span><span class="sxs-lookup"><span data-stu-id="6213d-128">Identifies the object type and attribute names for a specific source (external) Management Agent instance.</span></span> <span data-ttu-id="6213d-129">如果特定管理代理不具备此元素，则会假定该代理使用的是默认的对象类型（“person”）和属性名称（“uid”）。</span><span class="sxs-lookup"><span data-stu-id="6213d-129">If this element is not present for a specific Management Agent, then the default object type (“person”) and attribute names (“uid”) are assumed.</span></span> <span data-ttu-id="6213d-130">多个`SourceMA`允许的元素。</span><span class="sxs-lookup"><span data-stu-id="6213d-130">Multiple `SourceMA` elements are allowed.</span></span>  
  
 <span data-ttu-id="6213d-131">**属性： 命名**-源 （外部） 的名称管理代理。</span><span class="sxs-lookup"><span data-stu-id="6213d-131">**Attribute: name** - The name of the source (external) Management Agent.</span></span> <span data-ttu-id="6213d-132">此名称必须与至少一种`sourceMA`属性名称从`Application`元素。</span><span class="sxs-lookup"><span data-stu-id="6213d-132">This name must match at least one of the `sourceMA` attribute names from the `Application` elements.</span></span>  
  
 <span data-ttu-id="6213d-133">**属性： objectType** -可选的; 默认值是`person`。</span><span class="sxs-lookup"><span data-stu-id="6213d-133">**Attribute: objectType** - Optional; default is `person`.</span></span> <span data-ttu-id="6213d-134">如果提供的外部的用户 Id 的对象类型名称不是`person`，它应在此处指定。</span><span class="sxs-lookup"><span data-stu-id="6213d-134">If the object type name that provides the external UserId is not `person`, it should be specified here.</span></span>  
  
 <span data-ttu-id="6213d-135">**属性： 属性**-可选的; 默认值是`uid`。</span><span class="sxs-lookup"><span data-stu-id="6213d-135">**Attribute: attribute** - Optional; default is `uid`.</span></span> <span data-ttu-id="6213d-136">如果提供的外部的用户 Id 的属性名称不是`uid`，你可以在此处指定它。</span><span class="sxs-lookup"><span data-stu-id="6213d-136">If the attribute name that provides the external UserId is not `uid`, you can specify it here.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6213d-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6213d-137">See Also</span></span>  
 [<span data-ttu-id="6213d-138">如何使用 ENTSSO 管理代理</span><span class="sxs-lookup"><span data-stu-id="6213d-138">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)