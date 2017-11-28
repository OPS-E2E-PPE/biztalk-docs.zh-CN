---
title: "ImportParties 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87d43e2c-401c-4450-ad9b-2528086b99e4
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15edad97134d3dbccc6f4b1af9395cb0bc01febd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importparties-command"></a><span data-ttu-id="15796-102">ImportParties 命令</span><span class="sxs-lookup"><span data-stu-id="15796-102">ImportParties Command</span></span>
<span data-ttu-id="15796-103">从导入的企业到企业方和协议中配置数据库的源 XML 绑定文件而不导入任何应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="15796-103">Imports the business-to-business parties and agreements from a source XML binding file in the configuration database, without importing any of the application artifacts.</span></span> <span data-ttu-id="15796-104">有关详细信息，请参阅**备注**本主题中。</span><span class="sxs-lookup"><span data-stu-id="15796-104">For more information, see **Remarks** in this topic.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="15796-105">此命令是新开头 **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，和任何更高版本。</span><span class="sxs-lookup"><span data-stu-id="15796-105">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="15796-106">绑定中生成文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]没有指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="15796-106">Binding files generated in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have an application specified.</span></span> <span data-ttu-id="15796-107">它们被导入到默认的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="15796-107">They are imported into the default application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="15796-108">用法</span><span class="sxs-lookup"><span data-stu-id="15796-108">Usage</span></span>  
  <span data-ttu-id="15796-109">**BTSTask ImportParties-源**:*值*[**-ExcludeEdiFallbackSettings**] [**-服务器**:*值*] [**-数据库**:*值*]</span><span class="sxs-lookup"><span data-stu-id="15796-109">**BTSTask ImportParties -Source**:*value* [**-ExcludeEdiFallbackSettings**] [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="15796-110">Parameters</span><span class="sxs-lookup"><span data-stu-id="15796-110">Parameters</span></span>  
  
|<span data-ttu-id="15796-111">参数</span><span class="sxs-lookup"><span data-stu-id="15796-111">Parameter</span></span>|<span data-ttu-id="15796-112">必需</span><span class="sxs-lookup"><span data-stu-id="15796-112">Required</span></span>|<span data-ttu-id="15796-113">值</span><span class="sxs-lookup"><span data-stu-id="15796-113">Value</span></span>|  
|---|---|---|  
|<span data-ttu-id="15796-114">**源代码**</span><span class="sxs-lookup"><span data-stu-id="15796-114">**-Source**</span></span> | <span data-ttu-id="15796-115">必需</span><span class="sxs-lookup"><span data-stu-id="15796-115">Required</span></span> | <span data-ttu-id="15796-116">要读取的 XML 绑定文件路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="15796-116">The path and file name of the XML binding file to read.</span></span>|
|<span data-ttu-id="15796-117">**-ExcludeEdiFallbackSettings**</span><span class="sxs-lookup"><span data-stu-id="15796-117">**-ExcludeEdiFallbackSettings**</span></span> | <span data-ttu-id="15796-118">可选</span><span class="sxs-lookup"><span data-stu-id="15796-118">Optional</span></span> | <span data-ttu-id="15796-119">如果指定，将从绑定文件排除 edi 回退 （x12 和 edifact） 设置。</span><span class="sxs-lookup"><span data-stu-id="15796-119">If specified, it excludes edi fallback (x12 and edifact) settings from the binding file.</span></span>  |
| <span data-ttu-id="15796-120">**服务器**</span><span class="sxs-lookup"><span data-stu-id="15796-120">**-Server**</span></span> | <span data-ttu-id="15796-121">可选</span><span class="sxs-lookup"><span data-stu-id="15796-121">Optional</span></span> | <span data-ttu-id="15796-122">承载 BizTalk 配置数据库的 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="15796-122">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="15796-123">**数据库**</span><span class="sxs-lookup"><span data-stu-id="15796-123">**-Database**</span></span> | <span data-ttu-id="15796-124">可选</span><span class="sxs-lookup"><span data-stu-id="15796-124">Optional</span></span> | <span data-ttu-id="15796-125">BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="15796-125">The name of the BizTalk configuration database.</span></span> |

## <a name="sample"></a><span data-ttu-id="15796-126">示例</span><span class="sxs-lookup"><span data-stu-id="15796-126">Sample</span></span>
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a><span data-ttu-id="15796-127">注释</span><span class="sxs-lookup"><span data-stu-id="15796-127">Remarks</span></span>
<span data-ttu-id="15796-128">如果绑定文件还包含应用程序项目，然后将不导入它们。</span><span class="sxs-lookup"><span data-stu-id="15796-128">If the binding file also has application artifacts, then they are not imported.</span></span> <span data-ttu-id="15796-129">将导入仅方和协议。</span><span class="sxs-lookup"><span data-stu-id="15796-129">Only parties and agreements are imported.</span></span>