---
title: 组件接口中的标准方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, standard methods
- methods, viewing
- methods, component interfaces
- methods, changing
ms.assetid: 2273d946-3fc8-4b2d-a6a1-9e4f0da74d5b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eecb56f262a56e6567b44b146c631542cb1ceda6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994822"
---
# <a name="standard-methods-in-component-interfaces"></a>组件接口中的标准方法
组件接口的标准方法如下：  
  
- `Create`  
  
- `Find`  
  
- `Get`  
  
- `Save`  
  
  只有基础组件中的这些方法可用。 例如，如果基础组件不包含 `Add` 功能，则 `Create` 不可用。  
  
## <a name="viewing-or-changing-available-methods"></a>查看或更改可用方法  
  
#### <a name="to-view-or-change-available-methods"></a>若要查看或更改可用方法  
  
1.  打开组件接口**属性**对话框。  
  
     ![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")  
  
2.  单击**标准方法**选项卡。  
  
3.  选择所需的方法，然后依次**确定**。  
  
## <a name="see-also"></a>请参阅  
 [如何创建组件接口](../core/how-to-create-component-interfaces.md)   
 [附件 C：使用组件接口](../core/appendix-c-using-component-interfaces.md)