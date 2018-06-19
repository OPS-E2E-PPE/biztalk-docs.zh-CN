---
title: ExportParties 命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b421c8ed-d505-48ba-9d1d-8519c9d51750
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca525872ccc1cd941673189c4ac176fc4631f22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245813"
---
# <a name="exportparties-command"></a><span data-ttu-id="23d85-102">ExportParties 命令</span><span class="sxs-lookup"><span data-stu-id="23d85-102">ExportParties Command</span></span>
<span data-ttu-id="23d85-103">导出到 XML 绑定文件的所有方和协议。</span><span class="sxs-lookup"><span data-stu-id="23d85-103">Exports all the parties and agreements to an XML bindings file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23d85-104">此命令是新开头 **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，和任何更高版本。</span><span class="sxs-lookup"><span data-stu-id="23d85-104">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>

## <a name="usage"></a><span data-ttu-id="23d85-105">用法</span><span class="sxs-lookup"><span data-stu-id="23d85-105">Usage</span></span>
  <span data-ttu-id="23d85-106">**BTSTask ExportParties-目标**:*值*[**-服务器**:*值*] [**-数据库**:*值*]</span><span class="sxs-lookup"><span data-stu-id="23d85-106">**BTSTask ExportParties -Destination**:*value* [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="23d85-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="23d85-107">Parameters</span></span>

|<span data-ttu-id="23d85-108">参数</span><span class="sxs-lookup"><span data-stu-id="23d85-108">Parameter</span></span>|<span data-ttu-id="23d85-109">必需</span><span class="sxs-lookup"><span data-stu-id="23d85-109">Required</span></span>|<span data-ttu-id="23d85-110">值</span><span class="sxs-lookup"><span data-stu-id="23d85-110">Value</span></span>|  
|---|---|---|  
| <span data-ttu-id="23d85-111">**-目标**</span><span class="sxs-lookup"><span data-stu-id="23d85-111">**-Destination**</span></span> | <span data-ttu-id="23d85-112">必需</span><span class="sxs-lookup"><span data-stu-id="23d85-112">Required</span></span> | <span data-ttu-id="23d85-113">要写入的 XML 绑定文件的路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="23d85-113">Path and file name of the XML binding file to write.</span></span> |
| <span data-ttu-id="23d85-114">**服务器**</span><span class="sxs-lookup"><span data-stu-id="23d85-114">**-Server**</span></span> | <span data-ttu-id="23d85-115">可选</span><span class="sxs-lookup"><span data-stu-id="23d85-115">Optional</span></span> | <span data-ttu-id="23d85-116">承载 BizTalk 配置数据库的 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="23d85-116">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="23d85-117">**数据库**</span><span class="sxs-lookup"><span data-stu-id="23d85-117">**-Database**</span></span> | <span data-ttu-id="23d85-118">可选</span><span class="sxs-lookup"><span data-stu-id="23d85-118">Optional</span></span> | <span data-ttu-id="23d85-119">BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="23d85-119">The name of the BizTalk configuration database.</span></span>|

## <a name="sample"></a><span data-ttu-id="23d85-120">示例</span><span class="sxs-lookup"><span data-stu-id="23d85-120">Sample</span></span>
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a><span data-ttu-id="23d85-121">注释</span><span class="sxs-lookup"><span data-stu-id="23d85-121">Remarks</span></span>
  <span data-ttu-id="23d85-122">导出仅方、 协议和 EDI 回退设置。</span><span class="sxs-lookup"><span data-stu-id="23d85-122">Only parties, agreements, and EDI fallback settings are exported.</span></span> <span data-ttu-id="23d85-123">不导出任何应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="23d85-123">No application artifacts are exported.</span></span>
