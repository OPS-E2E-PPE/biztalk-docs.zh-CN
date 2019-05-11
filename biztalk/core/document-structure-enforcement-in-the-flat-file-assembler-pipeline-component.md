---
title: 文档结构强制规定在平面文件组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], document structure
ms.assetid: 3ac75706-1d4d-443a-a4bf-af8f79a6a092
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 028f09b50cf4abd40475163d568e220087fd1f44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350945"
---
# <a name="document-structure-enforcement-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="1a584-102">平面文件组装器管道组件中的文档结构强制规定</span><span class="sxs-lookup"><span data-stu-id="1a584-102">Document Structure Enforcement in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="1a584-103">如果在平面文件组装器中显式引用文档或信封架构，则平面文件组装器可确保仅处理消息类型与所引用的架构相应的文档。</span><span class="sxs-lookup"><span data-stu-id="1a584-103">If document or envelope schemas are explicitly referenced in the Flat File Assembler, the Flat File Assembler ensures that only documents with the message type corresponding to referenced schemas are processed.</span></span> <span data-ttu-id="1a584-104">不会对其他所有文档进行处理，即使可能已为这些文档部署了架构也是如此。</span><span class="sxs-lookup"><span data-stu-id="1a584-104">All the other documents are not processed even though a schema may be deployed for them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a584-105">信封架构仅取自第一条消息。</span><span class="sxs-lookup"><span data-stu-id="1a584-105">The envelope schema is taken from the first message only.</span></span> <span data-ttu-id="1a584-106">信封的属性始终取自第一条消息。</span><span class="sxs-lookup"><span data-stu-id="1a584-106">The properties for the envelope are always taken from the first message.</span></span>