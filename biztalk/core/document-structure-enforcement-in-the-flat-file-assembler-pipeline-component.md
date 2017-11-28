---
title: "文档中的平面文件汇编管道组件的结构强制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], document structure
ms.assetid: 3ac75706-1d4d-443a-a4bf-af8f79a6a092
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb35c7b31eda69d03d532d13d975d618d4f36f76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="11a7a-102">平面文件汇编管道组件中的文档结构强制</span><span class="sxs-lookup"><span data-stu-id="11a7a-102">Document Structure Enforcement in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="11a7a-103">如果在平面文件组装器中显式引用文档或信封架构，则平面文件组装器可确保仅处理消息类型与所引用的架构相应的文档。</span><span class="sxs-lookup"><span data-stu-id="11a7a-103">If document or envelope schemas are explicitly referenced in the Flat File Assembler, the Flat File Assembler ensures that only documents with the message type corresponding to referenced schemas are processed.</span></span> <span data-ttu-id="11a7a-104">不会对其他所有文档进行处理，即使可能已为这些文档部署了架构也是如此。</span><span class="sxs-lookup"><span data-stu-id="11a7a-104">All the other documents are not processed even though a schema may be deployed for them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11a7a-105">信封架构仅取自第一条消息。</span><span class="sxs-lookup"><span data-stu-id="11a7a-105">The envelope schema is taken from the first message only.</span></span> <span data-ttu-id="11a7a-106">信封的属性始终取自第一条消息。</span><span class="sxs-lookup"><span data-stu-id="11a7a-106">The properties for the envelope are always taken from the first message.</span></span>