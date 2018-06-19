---
title: 文档中的平面文件汇编管道组件的结构强制 |Microsoft 文档
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
ms.openlocfilehash: bb35c7b31eda69d03d532d13d975d618d4f36f76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238701"
---
# <a name="document-structure-enforcement-in-the-flat-file-assembler-pipeline-component"></a>平面文件汇编管道组件中的文档结构强制
如果在平面文件组装器中显式引用文档或信封架构，则平面文件组装器可确保仅处理消息类型与所引用的架构相应的文档。 不会对其他所有文档进行处理，即使可能已为这些文档部署了架构也是如此。  
  
> [!NOTE]
>  信封架构仅取自第一条消息。 信封的属性始终取自第一条消息。