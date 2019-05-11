---
title: 如何帮助安全组件接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, helping to secure
- security, component interfaces
ms.assetid: 03b2af44-78e7-4fdc-bfa3-7697b2a60986
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca6e0dcbd265dbfcdc6f128f2ff7b58e301f2e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385029"
---
# <a name="how-to-help-secure-component-interfaces"></a>如何帮助保护组件接口
在可以开始测试组件接口之前，必须为其来设置安全性。 以下过程描述如何配置组件接口安全性的 PeopleSoft 版本 8.4，但你可以使用 8.1 版的过程。  
  
### <a name="to-configure-interface-security"></a>若要配置接口安全性  
  
1.  展开**PeopleTools**，展开**安全**，展开**用户配置文件**，然后展开**权限与角色**。  
  
     ![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")  
  
2.  单击**权限列表**。  
  
3.  单击 **“搜索”**。  
  
     ![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")  
  
4.  在中**权限列出了搜索**窗格中，选择相关的权限列表。  
  
     将显示以下窗口。  
  
     ![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")  
  
5.  单击右箭头旁边**单一登录时间**选项卡以显示更多选项卡。  
  
     ![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")  
  
6.  单击**组件接口**选项卡。  
  
7.  单击 + （加号） 可以向其中添加新行**组件接口**列表。  
  
     可以在其中键入组件接口名称将出现的字段。  
  
     ![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")  
  
8.  键入组件接口名称，然后单击**编辑**。  
  
     此示例中使用组件接口 AR_ITEM_AGENT。  
  
     ![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")  
  
9. 在列表中，选择每个方法所需的访问级别，然后单击**确定**。  
  
     将显示以下窗口。  
  
     ![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")  
  
10. 在右窗格中，向下滚动并单击**保存**。  
  
## <a name="see-also"></a>请参阅  
 [附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)   
 [附录 c:使用组件接口](../core/appendix-c-using-component-interfaces.md)