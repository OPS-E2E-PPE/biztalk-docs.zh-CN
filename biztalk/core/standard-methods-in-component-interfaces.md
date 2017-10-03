---
title: "组件接口中的标准方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, standard methods
- methods, viewing
- methods, component interfaces
- methods, changing
ms.assetid: 2273d946-3fc8-4b2d-a6a1-9e4f0da74d5b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44b3977a3921d92b1f3f83dd3e744f14b5709fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="standard-methods-in-component-interfaces"></a>组件接口中的标准方法
组件接口的标准方法如下：  
  
-   `Create`  
  
-   `Find`  
  
-   `Get`  
  
-   `Save`  
  
 只有基础组件中的这些方法可用。 例如，如果基础组件不包含 `Add` 功能，则 `Create` 不可用。  
  
## <a name="viewing-or-changing-available-methods"></a>查看或更改可用方法  
  
#### <a name="to-view-or-change-available-methods"></a>若要查看或更改可用的方法  
  
1.  打开组件接口**属性**对话框。  
  
     ![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")  
  
2.  单击**标准方法**选项卡。  
  
3.  选择所需的方法，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建组件接口](../core/how-to-create-component-interfaces.md)   
 [附录 c： 使用组件接口](../core/appendix-c-using-component-interfaces.md)