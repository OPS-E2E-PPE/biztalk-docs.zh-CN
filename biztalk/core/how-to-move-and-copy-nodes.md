---
title: "如何移动和复制节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4f1ec14-c607-4da3-9139-73a61963b819
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55901e9ba6b27d05dccce0e547df618123ab466
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-and-copy-nodes"></a>如何移动和复制节点
您可能会遇到要将现有节点移动到架构树中的其他位置的情况。 还可以通过创建现有节点的副本，然后将其粘贴到架构树中的其他位置来节约时间。 本主题介绍了执行这些任务的逐步说明。  
  
> [!NOTE]
>  BizTalk 编辑器仅支持在架构内复制和粘贴节点，而不支持在架构之间进行这些操作。  
  
### <a name="to-move-a-node-within-a-schema"></a>在架构内移动节点  
  
1.  如果需要，可以展开架构树以同时显示要移动的节点和要将该节点移动到的位置。 有关展开和折叠架构树视图的详细信息，请参阅[管理架构树视图](../core/how-to-manage-the-schema-tree-view.md)。  
  
2.  单击要移动的节点并按住鼠标按钮，将其拖至树中的其他位置。  
  
> [!NOTE]
>  开始在架构树中向上或向下拖动节点时，鼠标指针将变为上箭头、下箭头或子箭头。 此箭头指示释放鼠标按钮时节点将放置到的位置：节点之前、节点之后或作为节点的子节点。  
  
#### <a name="to-copy-a-node-within-a-schema"></a>在架构内复制节点  
  
1.  右键单击你想要复制，，然后单击该节点**复制**。  
  
2.  右键单击**记录**要向其中插入复制节点，，然后单击的节点或组节点**粘贴**。  
  
     复制的节点的副本放在末尾的子节点**记录**节点或你在步骤 2 中所选的组节点。  
  
> [!NOTE]
>  只能在单个架构中使用剪切/复制/粘贴功能。 换句话说，您不能将节点从一个架构复制到另一个架构中。  
  
## <a name="see-also"></a>另请参阅  
 [使用现有节点](../core/working-with-existing-nodes.md)