---
title: 平面文件反汇编程序管道组件中的字符编码 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, Flat File Disassembler
- Flat File Disassembler [pipeline component], character encoding
ms.assetid: 0dbe24fb-c431-4edf-8aa9-4c040d6a7b32
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 839a3377f27417757e394c946fe96acc83752355
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231637"
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="a0f57-102">平面文件反汇编程序管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="a0f57-102">Character Encoding in the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="a0f57-103">平面文件拆装器组件使用以下算法来确定哪些编码要用于处理传入消息：</span><span class="sxs-lookup"><span data-stu-id="a0f57-103">The following algorithm is used by the Flat File Disassembler component to determine which encoding to use for processing an incoming message:</span></span>  
  
1.  <span data-ttu-id="a0f57-104">如果数据中存在字节顺序标记，则根据该标记确定编码信息。</span><span class="sxs-lookup"><span data-stu-id="a0f57-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span> <span data-ttu-id="a0f57-105">此编码的信息不会保留反汇编程序 (即，不保存到**XMLNorm.SourceCharset**属性)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-105">This encoding information is not preserved by the disassembler (that is, it is not saved to the **XMLNorm.SourceCharset** property).</span></span>  
  
2.  <span data-ttu-id="a0f57-106">否则为如果**IBaseMessagePart.Charset**属性设置，则使用此处指定该编码方式。</span><span class="sxs-lookup"><span data-stu-id="a0f57-106">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3.  <span data-ttu-id="a0f57-107">或者，如果标题或文档架构包含代码页信息，则使用该信息。</span><span class="sxs-lookup"><span data-stu-id="a0f57-107">Otherwise, if the header or document schema contains codepage information, it is used.</span></span>  
  
4.  <span data-ttu-id="a0f57-108">否则，将使用 UTF-8 编码。</span><span class="sxs-lookup"><span data-stu-id="a0f57-108">Otherwise, UTF-8 encoding is used.</span></span>  
  
 <span data-ttu-id="a0f57-109">于上述情况 2、 3 和 4，拆装器会将编码信息保存在消息上下文中**XMLNorm.SourceCharset**属性。</span><span class="sxs-lookup"><span data-stu-id="a0f57-109">For the preceding cases 2, 3, and 4, the disassembler saves the encoding information on the message context in the **XMLNorm.SourceCharset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f57-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0f57-110">See Also</span></span>  
 <span data-ttu-id="a0f57-111">[平面文件反汇编程序管道组件](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="a0f57-111">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="a0f57-112">[如何配置平面文件反汇编程序管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="a0f57-112">[How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="a0f57-113">管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="a0f57-113">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)