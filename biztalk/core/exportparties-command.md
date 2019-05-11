---
title: ExportParties 命令 |Microsoft Docs
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
ms.openlocfilehash: 63245cf72306af5bb4c28552a037ce89d8e6bfe8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345915"
---
# <a name="exportparties-command"></a><span data-ttu-id="57375-102">ExportParties 命令</span><span class="sxs-lookup"><span data-stu-id="57375-102">ExportParties Command</span></span>
<span data-ttu-id="57375-103">将所有参与方和协议导出到 XML 绑定文件。</span><span class="sxs-lookup"><span data-stu-id="57375-103">Exports all the parties and agreements to an XML bindings file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57375-104">此命令将新开头**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**，和任何更高版本。</span><span class="sxs-lookup"><span data-stu-id="57375-104">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>

## <a name="usage"></a><span data-ttu-id="57375-105">用法</span><span class="sxs-lookup"><span data-stu-id="57375-105">Usage</span></span>
  <span data-ttu-id="57375-106">**BTSTask ExportParties-目标**:*值*[**-Server**:*值*] [**-数据库**:*值*]</span><span class="sxs-lookup"><span data-stu-id="57375-106">**BTSTask ExportParties -Destination**:*value* [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="57375-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="57375-107">Parameters</span></span>

|<span data-ttu-id="57375-108">参数</span><span class="sxs-lookup"><span data-stu-id="57375-108">Parameter</span></span>|<span data-ttu-id="57375-109">Required</span><span class="sxs-lookup"><span data-stu-id="57375-109">Required</span></span>|<span data-ttu-id="57375-110">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="57375-110">Value</span></span>|  
|---|---|---|  
| <span data-ttu-id="57375-111">**-Destination**</span><span class="sxs-lookup"><span data-stu-id="57375-111">**-Destination**</span></span> | <span data-ttu-id="57375-112">Required</span><span class="sxs-lookup"><span data-stu-id="57375-112">Required</span></span> | <span data-ttu-id="57375-113">要写入的 XML 绑定文件的路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="57375-113">Path and file name of the XML binding file to write.</span></span> |
| <span data-ttu-id="57375-114">**-Server**</span><span class="sxs-lookup"><span data-stu-id="57375-114">**-Server**</span></span> | <span data-ttu-id="57375-115">可选</span><span class="sxs-lookup"><span data-stu-id="57375-115">Optional</span></span> | <span data-ttu-id="57375-116">承载 BizTalk 配置数据库的 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="57375-116">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="57375-117">**-Database**</span><span class="sxs-lookup"><span data-stu-id="57375-117">**-Database**</span></span> | <span data-ttu-id="57375-118">可选</span><span class="sxs-lookup"><span data-stu-id="57375-118">Optional</span></span> | <span data-ttu-id="57375-119">BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="57375-119">The name of the BizTalk configuration database.</span></span>|

## <a name="sample"></a><span data-ttu-id="57375-120">示例</span><span class="sxs-lookup"><span data-stu-id="57375-120">Sample</span></span>
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a><span data-ttu-id="57375-121">备注</span><span class="sxs-lookup"><span data-stu-id="57375-121">Remarks</span></span>
  <span data-ttu-id="57375-122">导出的参与方、 协议和 EDI 回退设置。</span><span class="sxs-lookup"><span data-stu-id="57375-122">Only parties, agreements, and EDI fallback settings are exported.</span></span> <span data-ttu-id="57375-123">导出无应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="57375-123">No application artifacts are exported.</span></span>
