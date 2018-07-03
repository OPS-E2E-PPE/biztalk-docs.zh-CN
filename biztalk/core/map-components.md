---
title: 映射组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper, output
- maps, file type
- maps, file contents
- BizTalk Mapper, file type
- maps, components
ms.assetid: be438d21-80a8-49d8-bd08-d85618ab23de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1590ad1450453602b4dd5f25b2d52a4364787af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996766"
---
# <a name="map-components"></a><span data-ttu-id="de045-102">映射组件</span><span class="sxs-lookup"><span data-stu-id="de045-102">Map Components</span></span>
<span data-ttu-id="de045-103">映射的大多数组件存储在映射文件（扩展名为 .btm）中。</span><span class="sxs-lookup"><span data-stu-id="de045-103">Map files (having a .btm extension) store most of the components of a map.</span></span> <span data-ttu-id="de045-104">该文件中存储的项包括：</span><span class="sxs-lookup"><span data-stu-id="de045-104">Items stored in the file include:</span></span>  
  
- <span data-ttu-id="de045-105">对源架构和目标架构的引用</span><span class="sxs-lookup"><span data-stu-id="de045-105">References to source and destination schemas</span></span>  
  
- <span data-ttu-id="de045-106">链接，包括链接属性</span><span class="sxs-lookup"><span data-stu-id="de045-106">Links, including the link properties</span></span>  
  
- <span data-ttu-id="de045-107">Functoid 及其属性，例如输入参数</span><span class="sxs-lookup"><span data-stu-id="de045-107">Functoids with their properties such as input parameters</span></span>  
  
- <span data-ttu-id="de045-108">其他属性，例如与网格和映射本身关联的属性</span><span class="sxs-lookup"><span data-stu-id="de045-108">Other miscellaneous properties such as those associated with the grid and the map itself.</span></span>  
  
  <span data-ttu-id="de045-109">虽然 BizTalk 映射器将 .btm 文件中的映射编译为可扩展样式表语言转换 (XSLT) 文件，但 XSLT 并不是该文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="de045-109">Although BizTalk Mapper compiles the map in the .btm file into an Extensible Stylesheet Transformations (XSLT) file, the XSLT is not part of the file.</span></span> <span data-ttu-id="de045-110">只有在编译项目或验证映射时，BizTalk 映射器才会为映射生成 XSLT。</span><span class="sxs-lookup"><span data-stu-id="de045-110">BizTalk Mapper produces the XSLT for the map only when you compile the project or when you validate the map.</span></span> <span data-ttu-id="de045-111">BizTalk 映射器将 XSLT 打包为项目程序集的一部分。</span><span class="sxs-lookup"><span data-stu-id="de045-111">BizTalk Mapper packages the XSLT as part of the project assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de045-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="de045-112">See Also</span></span>  
 <span data-ttu-id="de045-113">[映射](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="de045-113">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="de045-114">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="de045-114">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)