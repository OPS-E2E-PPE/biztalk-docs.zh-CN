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
ms.openlocfilehash: 09e59f51aa6d99fbd9b1351087a403350cc22a1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382214"
---
# <a name="importparties-command"></a><span data-ttu-id="892a2-102">ImportParties 命令</span><span class="sxs-lookup"><span data-stu-id="892a2-102">ImportParties Command</span></span>
<span data-ttu-id="892a2-103">从导入企业到企业参与方和协议配置数据库中的源 XML 绑定文件而无需导入的任何应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="892a2-103">Imports the business-to-business parties and agreements from a source XML binding file in the configuration database, without importing any of the application artifacts.</span></span> <span data-ttu-id="892a2-104">有关详细信息，请参阅**备注**本主题中。</span><span class="sxs-lookup"><span data-stu-id="892a2-104">For more information, see **Remarks** in this topic.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="892a2-105">此命令将新开头**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**，和任何更高版本。</span><span class="sxs-lookup"><span data-stu-id="892a2-105">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="892a2-106">绑定文件中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不具有指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="892a2-106">Binding files generated in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have an application specified.</span></span> <span data-ttu-id="892a2-107">它们是导入到默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="892a2-107">They are imported into the default application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="892a2-108">用法</span><span class="sxs-lookup"><span data-stu-id="892a2-108">Usage</span></span>  
  <span data-ttu-id="892a2-109">**BTSTask ImportParties -Source**:*value* [**-ExcludeEdiFallbackSettings**] [**-Server**:*value*] [**-Database**:*value*]</span><span class="sxs-lookup"><span data-stu-id="892a2-109">**BTSTask ImportParties -Source**:*value* [**-ExcludeEdiFallbackSettings**] [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="892a2-110">Parameters</span><span class="sxs-lookup"><span data-stu-id="892a2-110">Parameters</span></span>  
  
|<span data-ttu-id="892a2-111">参数</span><span class="sxs-lookup"><span data-stu-id="892a2-111">Parameter</span></span>|<span data-ttu-id="892a2-112">Required</span><span class="sxs-lookup"><span data-stu-id="892a2-112">Required</span></span>|<span data-ttu-id="892a2-113">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="892a2-113">Value</span></span>|  
|---|---|---|  
|<span data-ttu-id="892a2-114">**-Source**</span><span class="sxs-lookup"><span data-stu-id="892a2-114">**-Source**</span></span> | <span data-ttu-id="892a2-115">Required</span><span class="sxs-lookup"><span data-stu-id="892a2-115">Required</span></span> | <span data-ttu-id="892a2-116">要读取的 XML 绑定文件的路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="892a2-116">The path and file name of the XML binding file to read.</span></span>|
|<span data-ttu-id="892a2-117">**-ExcludeEdiFallbackSettings**</span><span class="sxs-lookup"><span data-stu-id="892a2-117">**-ExcludeEdiFallbackSettings**</span></span> | <span data-ttu-id="892a2-118">可选</span><span class="sxs-lookup"><span data-stu-id="892a2-118">Optional</span></span> | <span data-ttu-id="892a2-119">如果指定，系统会从绑定文件中排除 edi 回退 （x12 和 edifact） 设置。</span><span class="sxs-lookup"><span data-stu-id="892a2-119">If specified, it excludes edi fallback (x12 and edifact) settings from the binding file.</span></span>  |
| <span data-ttu-id="892a2-120">**-Server**</span><span class="sxs-lookup"><span data-stu-id="892a2-120">**-Server**</span></span> | <span data-ttu-id="892a2-121">可选</span><span class="sxs-lookup"><span data-stu-id="892a2-121">Optional</span></span> | <span data-ttu-id="892a2-122">承载 BizTalk 配置数据库的 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="892a2-122">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="892a2-123">**-Database**</span><span class="sxs-lookup"><span data-stu-id="892a2-123">**-Database**</span></span> | <span data-ttu-id="892a2-124">可选</span><span class="sxs-lookup"><span data-stu-id="892a2-124">Optional</span></span> | <span data-ttu-id="892a2-125">BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="892a2-125">The name of the BizTalk configuration database.</span></span> |

## <a name="sample"></a><span data-ttu-id="892a2-126">示例</span><span class="sxs-lookup"><span data-stu-id="892a2-126">Sample</span></span>
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a><span data-ttu-id="892a2-127">备注</span><span class="sxs-lookup"><span data-stu-id="892a2-127">Remarks</span></span>
<span data-ttu-id="892a2-128">如果绑定文件也具有应用程序项目，然后它们将不导入。</span><span class="sxs-lookup"><span data-stu-id="892a2-128">If the binding file also has application artifacts, then they are not imported.</span></span> <span data-ttu-id="892a2-129">导入仅参与方和协议。</span><span class="sxs-lookup"><span data-stu-id="892a2-129">Only parties and agreements are imported.</span></span>