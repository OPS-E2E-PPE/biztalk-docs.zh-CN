---
title: ImportParties 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d43e2c-401c-4450-ad9b-2528086b99e4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c25b913b6479b857fb7cee4aec10e6984f2195
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998534"
---
# <a name="importparties-command"></a><span data-ttu-id="8bcd0-102">ImportParties 命令</span><span class="sxs-lookup"><span data-stu-id="8bcd0-102">ImportParties Command</span></span>
<span data-ttu-id="8bcd0-103">从导入企业到企业参与方和协议配置数据库中的源 XML 绑定文件而无需导入的任何应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-103">Imports the business-to-business parties and agreements from a source XML binding file in the configuration database, without importing any of the application artifacts.</span></span> <span data-ttu-id="8bcd0-104">有关详细信息，请参阅**备注**本主题中。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-104">For more information, see **Remarks** in this topic.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="8bcd0-105">此命令将新开头**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**，和任何更高版本。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-105">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="8bcd0-106">绑定文件中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不具有指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-106">Binding files generated in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have an application specified.</span></span> <span data-ttu-id="8bcd0-107">它们被导入到默认的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-107">They are imported into the default application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="8bcd0-108">用法</span><span class="sxs-lookup"><span data-stu-id="8bcd0-108">Usage</span></span>  
  <span data-ttu-id="8bcd0-109">**BTSTask ImportParties-源**:*值*[**-ExcludeEdiFallbackSettings**] [**-Server**:*值*] [**-数据库**:*值*]</span><span class="sxs-lookup"><span data-stu-id="8bcd0-109">**BTSTask ImportParties -Source**:*value* [**-ExcludeEdiFallbackSettings**] [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8bcd0-110">Parameters</span><span class="sxs-lookup"><span data-stu-id="8bcd0-110">Parameters</span></span>  
  
|<span data-ttu-id="8bcd0-111">参数</span><span class="sxs-lookup"><span data-stu-id="8bcd0-111">Parameter</span></span>|<span data-ttu-id="8bcd0-112">Required</span><span class="sxs-lookup"><span data-stu-id="8bcd0-112">Required</span></span>|<span data-ttu-id="8bcd0-113">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="8bcd0-113">Value</span></span>|  
|---|---|---|  
|<span data-ttu-id="8bcd0-114">**-源**</span><span class="sxs-lookup"><span data-stu-id="8bcd0-114">**-Source**</span></span> | <span data-ttu-id="8bcd0-115">Required</span><span class="sxs-lookup"><span data-stu-id="8bcd0-115">Required</span></span> | <span data-ttu-id="8bcd0-116">要读取的 XML 绑定文件的路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-116">The path and file name of the XML binding file to read.</span></span>|
|<span data-ttu-id="8bcd0-117">**-ExcludeEdiFallbackSettings**</span><span class="sxs-lookup"><span data-stu-id="8bcd0-117">**-ExcludeEdiFallbackSettings**</span></span> | <span data-ttu-id="8bcd0-118">可选</span><span class="sxs-lookup"><span data-stu-id="8bcd0-118">Optional</span></span> | <span data-ttu-id="8bcd0-119">如果指定，系统会从绑定文件中排除 edi 回退 （x12 和 edifact） 设置。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-119">If specified, it excludes edi fallback (x12 and edifact) settings from the binding file.</span></span>  |
| <span data-ttu-id="8bcd0-120">**-服务器**</span><span class="sxs-lookup"><span data-stu-id="8bcd0-120">**-Server**</span></span> | <span data-ttu-id="8bcd0-121">可选</span><span class="sxs-lookup"><span data-stu-id="8bcd0-121">Optional</span></span> | <span data-ttu-id="8bcd0-122">承载 BizTalk 配置数据库的 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-122">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="8bcd0-123">**-数据库**</span><span class="sxs-lookup"><span data-stu-id="8bcd0-123">**-Database**</span></span> | <span data-ttu-id="8bcd0-124">可选</span><span class="sxs-lookup"><span data-stu-id="8bcd0-124">Optional</span></span> | <span data-ttu-id="8bcd0-125">BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-125">The name of the BizTalk configuration database.</span></span> |

## <a name="sample"></a><span data-ttu-id="8bcd0-126">示例</span><span class="sxs-lookup"><span data-stu-id="8bcd0-126">Sample</span></span>
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a><span data-ttu-id="8bcd0-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="8bcd0-127">Remarks</span></span>
<span data-ttu-id="8bcd0-128">如果绑定文件也具有应用程序项目，然后它们将不导入。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-128">If the binding file also has application artifacts, then they are not imported.</span></span> <span data-ttu-id="8bcd0-129">导入仅参与方和协议。</span><span class="sxs-lookup"><span data-stu-id="8bcd0-129">Only parties and agreements are imported.</span></span>