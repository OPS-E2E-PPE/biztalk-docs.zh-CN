---
title: 如何创建和修改适配器组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1eef051-2ed7-4e28-8cb9-0145d6c8ed76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff60beb673515421054863799f7445304a5be200
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339499"
---
# <a name="how-to-create-and-modify-an-adapter-group"></a>如何创建和修改适配器组
单一登录 (SSO) 的新功能之一是能够创建和修改适配器组。 顾名思义，适配器组是适配器的集合。 可以使用适配器组来组织为您的适配器的安全设置和其他属性。  
  
### <a name="to-create-and-modify-an-adapter-group"></a>若要创建和修改适配器组  
  
1.  使用 ssops 工具调用创建适配器组。  
  
     在关联的 XML 文件中，您必须设置为适配器组的组标志。  
  
2.  使用将一个或多个适配器添加到适配器组`ISSOPSAdmin.AddAdapterToAdapterGroup`。  
  
     此时，适配器组已准备好按预期方式工作。 如果有必要，您可以查看相关联的适配器的完整列表使用`ISSOPSAdmin.GetAdaptersForAdapterGroup`。  
  
3.  您可以修改适配器组使用的设置`ISSOPSAdmin.SetAdapterProperties`。  
  
4.  完成后，可以删除该适配器从适配器组使用`ISSOPSAdmin.RemoveAdapterFromAdapterGroup`。  
  
5.  最后，通过使用删除适配器组`ISSOAdmin.DeleteApplication`。  
  
     您也可改为使用删除适配器组`-delete`ssops 工具的命令。  
  
## <a name="see-also"></a>请参阅  
 [同步密码](../core/synchronizing-passwords.md)