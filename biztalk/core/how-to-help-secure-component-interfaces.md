---
title: 如何帮助安全组件接口 |Microsoft 文档
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
ms.openlocfilehash: 54136aaeae9578ae4e438c5bd8b95b902d618f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255213"
---
# <a name="how-to-help-secure-component-interfaces"></a>如何帮助保护组件接口
在开始测试组件接口前，必须为它设置安全性。 以下过程描述如何为 PeopleSoft 版本 8.4 配置组件接口安全性，但你可以为版本 8.1 使用过程。  
  
### <a name="to-configure-interface-security"></a>配置接口安全性  
  
1.  展开**PeopleTools**，展开**安全**，展开**用户配置文件**，然后展开**权限和角色**。  
  
     ![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")  
  
2.  单击**权限列表**。  
  
3.  单击 **“搜索”**。  
  
     ![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")  
  
4.  在**权限列出搜索**窗格中，选择相关的权限列表。  
  
     出现以下窗口。  
  
     ![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")  
  
5.  单击右箭头旁边**登录时间**选项卡以显示更多选项卡。  
  
     ![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")  
  
6.  单击**组件接口**选项卡。  
  
7.  单击 + （加号） 若要向其中添加新行**组件接口**列表。  
  
     出现一个字段，您可在其中键入组件接口名称。  
  
     ![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")  
  
8.  键入组件接口名称，然后单击**编辑**。  
  
     此示例使用组件接口 AR_ITEM_AGENT。  
  
     ![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")  
  
9. 在列表中，选择每个方法所需的访问级别，然后单击**确定**。  
  
     出现以下窗口。  
  
     ![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")  
  
10. 在右窗格中，向下滚动并单击**保存**。  
  
## <a name="see-also"></a>另请参阅  
 [附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)   
 [附录 c： 使用组件接口](../core/appendix-c-using-component-interfaces.md)