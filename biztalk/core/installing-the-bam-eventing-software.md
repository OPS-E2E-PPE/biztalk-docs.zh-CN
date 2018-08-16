---
title: 安装 Bam-eventing 软件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3638d34-f5a8-4ffd-99eb-d38aed4c0732
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca5d13e058799113d7847fe6377ce82c7e0a7ea5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000286"
---
# <a name="installing-the-bam-eventing-software"></a>安装 Bam-eventing 软件
若要实现 BAM 解决方案使用 BAM eventing Api 或 Windows Workflow Foundation 或 Windows Communication Foundation 应用程序要用于 Windows Workflow Foundation 的 BAM 侦听器配置，必须安装 Bam-eventing 软件使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。 此软件可以作为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时的一部分安装，也可以通过在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装应用程序中的“其他软件”下选择揃“BAM Eventing Support”来单独安装。  
  
### <a name="to-install-the-bam-eventing-software"></a>安装 BAM-Eventing 软件  
  
1. 使用具有管理员权限的帐户登录到将承载 WF 应用程序的计算机。  
  
2. 上运行安装程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装 CD。  
  
3. 清除所有选定的选项。 如果不执行此步骤，可能会安装不需要的软件。  
  
4. 展开**其他软件**，然后选择**Bam-eventing**复选框。  
  
5. 单击“下一步” 。  
  
6. 单击 **“安装”**。  
  
7. 安装过程完成后，单击**确定**。  
  
    BAM-Eventing 软件现在已安装完毕。  
  
> [!NOTE]
>  使用此方法安装 BAM 侦听器库不需要购买其他许可证。  
  
 如果你希望监视 BAM 侦听器的性能计数器数据，必须先使用 InstallUtil.exe 注册它们。  
  
### <a name="to-register-bam-interceptor-performance-counters-by-using-installutilexe"></a>使用 InstallUtil.exe 注册 BAM 侦听器性能计数器  
  
1. 启动**[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下**以管理员身份。  
  
2. 在命令提示符下输入以下命令：  
  
    InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll  
  
3. 类型**退出**，然后按 ENTER 以关闭命令提示符。  
  
    BAM 侦听器性能计数器现在处于可用状态。  
  
> [!NOTE]
>  默认情况下，只有管理员帐户和系统帐户具有在日志中记录性能数据的权限。 若要启用访问权限在[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]，添加用于运行工作流应用程序到 Performance Log Users 组的帐户。  
  
## <a name="see-also"></a>请参阅  
 [实现 BAM 解决方案](../core/implementing-bam-solutions.md)   
 [BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)