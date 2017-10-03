---
title: "如何创建和修改适配器组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1eef051-2ed7-4e28-8cb9-0145d6c8ed76
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6865de8eb67d9fe1a6ca8d93b7d2e6527ae36364
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-and-modify-an-adapter-group"></a>如何创建和修改适配器组
新功能的单一登录 (SSO) 之一是能够创建和修改适配器组。 顾名思义，适配器组是适配器的集合。 可以使用适配器组来组织为你的适配器的安全设置和其他属性。  
  
### <a name="to-create-and-modify-an-adapter-group"></a>若要创建和修改适配器组  
  
1.  通过调用 ssops 工具创建适配器组。  
  
     在关联的 XML 文件中，你必须将组标志设置为适配器组。  
  
2.  通过将一个或多个适配器添加到适配器组`ISSOPSAdmin.AddAdapterToAdapterGroup`。  
  
     此时，你的适配器组已准备好按预期方式工作。 如果有必要，你可以查看关联的适配器的完整列表使用`ISSOPSAdmin.GetAdaptersForAdapterGroup`。  
  
3.  你可以修改适配器组使用的设置`ISSOPSAdmin.SetAdapterProperties`。  
  
4.  完成后，你可以从适配器组使用删除适配器`ISSOPSAdmin.RemoveAdapterFromAdapterGroup`。  
  
5.  最后，可以通过使用删除适配器组`ISSOAdmin.DeleteApplication`。  
  
     你可以选择改为使用删除适配器组`-delete`ssops 工具的命令。  
  
## <a name="see-also"></a>另请参阅  
 [同步密码](../core/synchronizing-passwords.md)