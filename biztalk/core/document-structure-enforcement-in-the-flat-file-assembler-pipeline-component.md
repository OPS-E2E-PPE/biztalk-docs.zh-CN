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
# <a name="document-structure-enforcement-in-the-flat-file-assembler-pipeline-component"></a>平面文件组装器管道组件中的文档结构强制规定
如果在平面文件组装器中显式引用文档或信封架构，则平面文件组装器可确保仅处理消息类型与所引用的架构相应的文档。 不会对其他所有文档进行处理，即使可能已为这些文档部署了架构也是如此。  
  
> [!NOTE]
>  信封架构仅取自第一条消息。 信封的属性始终取自第一条消息。