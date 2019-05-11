---
title: 如何更改跟踪 QueryTimeout 值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [HAT], time-out limits
- HAT, time-out limits
ms.assetid: abc26f37-6537-42fa-81ff-bc8b758b4e10
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77e609b5b551fc5b8c97dac704ad31e4e413426c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387022"
---
# <a name="how-to-change-the-tracking-querytimeout-value"></a>如何更改跟踪 QueryTimeout 值
默认情况下，消息和服务实例跟踪将超时如果查询的运行时间超过 60 秒。 你可以在注册表中启用查询运行时间超过 60 秒的超时值。  
  
> [!CAUTION]
>  错误编辑注册表可能会严重损坏您的系统。 更改注册表之前，应当备份计算机中的所有重要数据。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的管理员组的成员身份登录。  
  
### <a name="to-change-the-query-timeout-value"></a>若要更改查询超时值  
  
1.  单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。  
  
2.  在注册表编辑器中，找到并单击以下注册表子项：  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0**  
  
3.  如果没有 Tracking 注册表子项，请转到步骤 6。  
  
4.  若要创建 Tracking 注册表子项，在**编辑**菜单，依次指向**新建**，然后单击**密钥**。  
  
5.  类型**跟踪**，然后按 ENTER。  
  
6.  找到并单击以下注册表子项：  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**  
  
7.  上**编辑**菜单，依次指向**新建**，然后单击**DWORD 值**。  
  
8.  类型**ConnectionTimeout**，然后按 ENTER。  
  
9. 右键单击**ConnectionTimeout**，然后单击**修改**。  
  
10. 在中**编辑 DWORD 值**对话框中，单击**十进制**。  
  
11. 在中**数值数据**框中，键入值以秒为单位，你想要的查询超时值，设置，然后单击**确定**。  
  
12. 在 **“文件”** 菜单中，单击 **“退出”**。  
  
    > [!NOTE]
    >  您可能需要关闭并重新打开 BizTalk Server 管理控制台中新的超时值的顺序才会生效。  
  
## <a name="see-also"></a>请参阅  
 [查看历史数据和跟踪数据](../core/viewing-historical-and-tracked-data.md)