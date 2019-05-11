---
title: 文档引用 URL 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Document Reference URL nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- definition files [BAM], related documents
ms.assetid: 38c8ae50-ed56-451c-9549-db852d4770e5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c9cbc37b48ad6592215723695b54edc17e834b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350965"
---
# <a name="document-reference-url-nodes"></a>文档引用 URL 节点
文档引用 URL 节点位于开发人员从知识工作者创建的观察模型导入的活动定义文件中。 文档引用 URL 节点包含对包含此活动与相关的文档的位置的引用。 这可以是文档的任何类型，例如活动表示采购订单审批工作流，文档引用 URL 可能指向底层采购订单文档。  
  
## <a name="working-with-document-reference-url-nodes"></a>使用文档引用 URL 节点  
 文档引用 URL 的数据源通常是**MessageRefURL** BizTalk Server 系统属性。 此外可以使用自定义架构的存储 Url 和将属性映射到文档引用 URL 从自定义架构。  
  
 请注意关于文档引用 Url 的项：  
  
-   您可以添加一个或多个文档引用 Url，但每个节点必须具有活动中的唯一名称。  
  
-   **MessageRefURL**在 WSS、 FILE 和 FTP 传输适配器的情况下的值仅填充填充文档引用 URL 节点所需的属性。  
  
-   尽管业务最终用户可以在 BAM 门户中查看此引用，引用 URL 的主要用途是允许自定义用户界面开发人员可以访问关联的文档信息，以便它们可以将其提交给最终用户。  在 BAM 门户中查看文档引用的详细信息，请参阅[相关文档](../core/related-documents.md)。  
  
## <a name="see-also"></a>请参阅  
 [“TPE 活动视图”节点](../core/tpe-activity-view-nodes.md)