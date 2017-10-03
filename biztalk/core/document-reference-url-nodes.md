---
title: "文档引用 URL 节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Document Reference URL nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- definition files [BAM], related documents
ms.assetid: 38c8ae50-ed56-451c-9549-db852d4770e5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7939a7e74483b8df192530fd9da2deafeda0681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="document-reference-url-nodes"></a>文档引用 URL 节点
文档引用 URL 节点位于开发人员从知识工作者创建的观察模型导入的活动定义文件中。 文档引用 URL 节点包含一个位置的引用，该位置包含与此活动相关的文档。 该文档可以是任何类型的文档，例如，对于表示采购订单审批工作流的活动，文档引用 URL 可能指向底层采购订单文档。  
  
## <a name="working-with-document-reference-url-nodes"></a>使用文档引用 URL 节点  
 文档引用 URL 的数据源通常是**MessageRefURL** BizTalk 服务器系统属性。 您还可以使用存储 URL 的自定义架构，然后将该属性映射到该自定义架构中的文档引用 URL。  
  
 关于文档引用 URL 的注意事项：  
  
-   您可以添加一个或多个文档引用 URL，但每个节点在活动内都必须具有唯一的名称。  
  
-   **MessageRefURL**填充文档引用 URL 节点所需的属性仅使用在 WSS、 文件和 FTP 传输适配器的情况下某个值填充。  
  
-   虽然业务最终用户可以在 BAM 门户中查看此引用，引用 URL 的主要目的是以允许自定义用户界面开发人员可以访问关联文档信息，以便它们可以将其提交给最终用户。  有关在 BAM 门户中查看的文档引用的详细信息，请参阅[相关文档](../core/related-documents.md)。  
  
## <a name="see-also"></a>另请参阅  
 [键入活动视图节点](../core/tpe-activity-view-nodes.md)