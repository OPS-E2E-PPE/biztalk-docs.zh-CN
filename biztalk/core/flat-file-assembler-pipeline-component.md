---
title: 平面文件汇编管道组件 |Microsoft 文档
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
ms.openlocfilehash: 385b1f8ea6c2ce707069cde522ea2f6712290be7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245861"
---
# <a name="flat-file-assembler-pipeline-component"></a><span data-ttu-id="b62c8-102">平面文件汇编管道组件</span><span class="sxs-lookup"><span data-stu-id="b62c8-102">Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="b62c8-103">平面文件组装器可以将单个文档组合到批中，并可以根据需要为批添加头部或尾部（或同时添加头部和尾部）。</span><span class="sxs-lookup"><span data-stu-id="b62c8-103">A Flat File Assembler combines individual documents into a batch and optionally adds a header or trailer (or both) to it.</span></span> <span data-ttu-id="b62c8-104">有关平面文件的详细信息，请参阅[分隔记录的平面文件消息](../core/flat-file-messages-with-delimited-records.md)。</span><span class="sxs-lookup"><span data-stu-id="b62c8-104">For more information about flat files, see [Flat File Messages with Delimited Records](../core/flat-file-messages-with-delimited-records.md).</span></span> <span data-ttu-id="b62c8-105">另请参阅[平面文件消息的位置记录](../core/flat-file-messages-with-positional-records.md)。</span><span class="sxs-lookup"><span data-stu-id="b62c8-105">Also see [Flat File Messages with Positional Records](../core/flat-file-messages-with-positional-records.md).</span></span>  
  
 <span data-ttu-id="b62c8-106">平面文件组装器管道组件不对传入 XML 消息进行验证。</span><span class="sxs-lookup"><span data-stu-id="b62c8-106">The Flat File Assembler pipeline component does not validate the incoming XML message.</span></span> <span data-ttu-id="b62c8-107">若要确保执行 XML 验证，请在发送管道的预组装阶段包括 XML 验证器组件。</span><span class="sxs-lookup"><span data-stu-id="b62c8-107">To ensure XML validation, include the XML Validator component in the Pre-Assemble stage of the send pipeline.</span></span>  
  
 <span data-ttu-id="b62c8-108">平面文件组装器管道组件仅支持 Microsoft .NET Framework 所支持的转换。</span><span class="sxs-lookup"><span data-stu-id="b62c8-108">The Flat File Assembler pipeline component only supports conversions supported by the Microsoft .NET Framework.</span></span> <span data-ttu-id="b62c8-109">其他任何转换可以通过写入自定义文本编写器来完成。</span><span class="sxs-lookup"><span data-stu-id="b62c8-109">Any additional conversion can be done by writing to a custom text writer.</span></span>  
  
 <span data-ttu-id="b62c8-110">有关配置平面文件汇编器管道组件的信息，请参阅[如何配置平面文件汇编管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="b62c8-110">For information about configuring the Flat File Assembler pipeline component, see [How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b62c8-111">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你无法将消息组合为一个交换。</span><span class="sxs-lookup"><span data-stu-id="b62c8-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you cannot assemble messages into one interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b62c8-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="b62c8-112">In This Section</span></span>  
  
-   [<span data-ttu-id="b62c8-113">平面文件汇编管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="b62c8-113">Character Encoding in the Flat File Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="b62c8-114">平面文件汇编管道组件中的文档结构强制</span><span class="sxs-lookup"><span data-stu-id="b62c8-114">Document Structure Enforcement in the Flat File Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="b62c8-115">保留在平面文件汇编管道组件的分隔符</span><span class="sxs-lookup"><span data-stu-id="b62c8-115">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)