---
title: 平面文件组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component]
ms.assetid: 3c851771-55b2-4d21-9291-d707dd66837c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 666a6612be354b1c5cda9f1c4f40a3702cadfb78
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387921"
---
# <a name="flat-file-assembler-pipeline-component"></a><span data-ttu-id="2241c-102">平面文件组装器管道组件</span><span class="sxs-lookup"><span data-stu-id="2241c-102">Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="2241c-103">平面文件组装器将单个文档组合到一批，并根据需要向其添加一个标头或尾部 （或两者）。</span><span class="sxs-lookup"><span data-stu-id="2241c-103">A Flat File Assembler combines individual documents into a batch and optionally adds a header or trailer (or both) to it.</span></span> <span data-ttu-id="2241c-104">有关平面文件的详细信息，请参阅[带有分隔记录的平面文件消息](../core/flat-file-messages-with-delimited-records.md)。</span><span class="sxs-lookup"><span data-stu-id="2241c-104">For more information about flat files, see [Flat File Messages with Delimited Records](../core/flat-file-messages-with-delimited-records.md).</span></span> <span data-ttu-id="2241c-105">另请参阅[带有位置记录的平面文件消息](../core/flat-file-messages-with-positional-records.md)。</span><span class="sxs-lookup"><span data-stu-id="2241c-105">Also see [Flat File Messages with Positional Records](../core/flat-file-messages-with-positional-records.md).</span></span>  
  
 <span data-ttu-id="2241c-106">平面文件组装器管道组件不会验证传入的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="2241c-106">The Flat File Assembler pipeline component does not validate the incoming XML message.</span></span> <span data-ttu-id="2241c-107">若要确保执行 XML 验证，发送管道的预组装阶段包括 XML 验证器组件。</span><span class="sxs-lookup"><span data-stu-id="2241c-107">To ensure XML validation, include the XML Validator component in the Pre-Assemble stage of the send pipeline.</span></span>  
  
 <span data-ttu-id="2241c-108">平面文件组装器管道组件仅支持 Microsoft.NET Framework 支持的转换。</span><span class="sxs-lookup"><span data-stu-id="2241c-108">The Flat File Assembler pipeline component only supports conversions supported by the Microsoft .NET Framework.</span></span> <span data-ttu-id="2241c-109">通过写入自定义文本编写器可以进行其他任何转换。</span><span class="sxs-lookup"><span data-stu-id="2241c-109">Any additional conversion can be done by writing to a custom text writer.</span></span>  
  
 <span data-ttu-id="2241c-110">有关配置平面文件组装器管道组件的信息，请参阅[如何配置平面文件组装器管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="2241c-110">For information about configuring the Flat File Assembler pipeline component, see [How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2241c-111">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，不能将消息组装为一个交换。</span><span class="sxs-lookup"><span data-stu-id="2241c-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you cannot assemble messages into one interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2241c-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="2241c-112">In This Section</span></span>  
  
-   [<span data-ttu-id="2241c-113">平面文件汇编程序管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="2241c-113">Character Encoding in the Flat File Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="2241c-114">平面文件汇编程序 管道组件中的文档结构强制规定</span><span class="sxs-lookup"><span data-stu-id="2241c-114">Document Structure Enforcement in the Flat File Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="2241c-115">保留平面文件汇编程序管道组件中的分隔符</span><span class="sxs-lookup"><span data-stu-id="2241c-115">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)