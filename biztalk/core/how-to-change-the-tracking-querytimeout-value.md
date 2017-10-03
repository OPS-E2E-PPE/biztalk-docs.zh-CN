---
title: "如何更改跟踪 QueryTimeout 值 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [HAT], time-out limits
- HAT, time-out limits
ms.assetid: abc26f37-6537-42fa-81ff-bc8b758b4e10
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca9f61466323e0b154bdeb0499cc5cee6e4ef10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-tracking-querytimeout-value"></a>如何更改跟踪查询超时值
默认情况下，如果查询的运行时间超过 60 秒，则消息和服务实例跟踪将超时。 您可以在注册表中更改该超时值，使查询的运行时间超过 60 秒。  
  
> [!CAUTION]
>  错误编辑注册表可能会严重损坏您的系统。 更改注册表之前，应当备份计算机中的所有重要数据。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-change-the-query-timeout-value"></a>更改查询超时值的步骤  
  
1.  单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。  
  
2.  在注册表编辑器中，找到并单击以下注册表子项：  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0**  
  
3.  如果没有 Tracking 注册表子项，则转到第 6 步。  
  
4.  若要创建一个跟踪子项，在**编辑**菜单上，指向**新建**，然后单击**密钥**。  
  
5.  类型**跟踪**，然后按 ENTER。  
  
6.  找到并单击以下注册表子项：  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**  
  
7.  上**编辑**菜单上，指向**新建**，然后单击**DWORD 值**。  
  
8.  类型**ConnectionTimeout**，然后按 ENTER。  
  
9. 右键单击**ConnectionTimeout**，然后单击**修改**。  
  
10. 在**编辑 DWORD 值**对话框中，单击**十进制**。  
  
11. 在**值数据**框中，键入值以秒为单位你想要的查询超时值，设置，然后单击**确定**。  
  
12. 在 **“文件”** 菜单中，单击 **“退出”**。  
  
    > [!NOTE]
    >  您可能需要关闭后再重新打开 BizTalk Server 管理控制台，才能使新的超时值生效。  
  
## <a name="see-also"></a>另请参阅  
 [查看历史记录和跟踪数据](../core/viewing-historical-and-tracked-data.md)