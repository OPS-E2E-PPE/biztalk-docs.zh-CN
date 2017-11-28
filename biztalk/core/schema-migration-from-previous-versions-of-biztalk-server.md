---
title: "从以前版本的 BizTalk Server 架构迁移 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bdc86401-2002-40b8-a919-2c00cf42b557
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1666e7cc8459fd4418e0ba0963caf5b654975805
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-migration-from-previous-versions-of-biztalk-server"></a><span data-ttu-id="c4f8c-102">从早期版本的 BizTalk Server 迁移架构</span><span class="sxs-lookup"><span data-stu-id="c4f8c-102">Schema Migration from Previous Versions of BizTalk Server</span></span>
<span data-ttu-id="c4f8c-103">此版本的 BizTalk Server 使用 XML 架构定义 (XSD) 语言来表示消息架构，而早期版本则使用精简 XML 数据 (XDR) 语法来表示消息架构。</span><span class="sxs-lookup"><span data-stu-id="c4f8c-103">This version of BizTalk Server uses XML Schema definition (XSD) language to represent message schemas, while previous versions used the XML-Data Reduced (XDR) syntax to represent message schemas.</span></span> <span data-ttu-id="c4f8c-104">若要从早期版本的 BizTalk Server 进行迁移，则必须将架构转换为使用 XSD，而不是使用 XDR。</span><span class="sxs-lookup"><span data-stu-id="c4f8c-104">If you are migrating from a previous version of BizTalk Server, you must convert your schemas to use XSD rather than XDR.</span></span>  
  
 <span data-ttu-id="c4f8c-105">若要将 BizTalk 架构从 XDR 语法转换为 XSD 语法，则需要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c4f8c-105">You need to perform the following tasks to convert a BizTalk schema from XDR syntax to XSD syntax:</span></span>  
  
-   <span data-ttu-id="c4f8c-106">将架构文件的扩展名从 .xdr 更改为 .xsd。</span><span class="sxs-lookup"><span data-stu-id="c4f8c-106">Change the extension of the schema file from.xdr to.xsd.</span></span>  
  
-   <span data-ttu-id="c4f8c-107">将重命名的架构添加到相应的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="c4f8c-107">Add the renamed schema to the appropriate BizTalk project.</span></span>  
  
-   <span data-ttu-id="c4f8c-108">在 BizTalk 编辑器中打开重命名的架构，将其从 XDR 转换为 XSD。</span><span class="sxs-lookup"><span data-stu-id="c4f8c-108">Convert the renamed schema from XDR to XSD by opening the schema in BizTalk Editor.</span></span>  
  
-   <span data-ttu-id="c4f8c-109">保存该架构，使其永久转换。</span><span class="sxs-lookup"><span data-stu-id="c4f8c-109">Make the conversion permanent by saving the schema.</span></span>  
  
 <span data-ttu-id="c4f8c-110">有关如何执行这些步骤的详细信息，请参阅[如何迁移到 XSD 架构的 XDR 架构](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="c4f8c-110">For detailed information about how to perform these steps, see [How to Migrate XDR Schemas to XSD Schemas](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f8c-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f8c-111">See Also</span></span>  
 <span data-ttu-id="c4f8c-112">[有关架构](../core/about-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="c4f8c-112">[About Schemas](../core/about-schemas.md) </span></span>  
 <span data-ttu-id="c4f8c-113">[如何将 XDR 架构迁移到 XSD 架构](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="c4f8c-113">[How to Migrate XDR Schemas to XSD Schemas](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md) </span></span>  
 [<span data-ttu-id="c4f8c-114">迁移的平面文件记录</span><span class="sxs-lookup"><span data-stu-id="c4f8c-114">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)