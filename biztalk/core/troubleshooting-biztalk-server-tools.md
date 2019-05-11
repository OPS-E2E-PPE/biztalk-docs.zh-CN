---
title: BizTalk Server 工具进行故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 038a5f5c-d6eb-42db-88d6-70f3deba7a8a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b492c4ee6d22c1eb360f24c60efee1c1106d3b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292928"
---
# <a name="troubleshooting-biztalk-server-tools"></a>BizTalk Server 工具进行故障排除
本主题提供有关使用附带的工具时遇到的常见问题的信息的一个集中的位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="known-issues"></a>已知问题  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a>BizTalk Server 工具和实用程序可能无法正常工作支持 UAC 的 Windows 系统上  
 **问题**  
  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持用户帐户控制 (UAC) 附带的工具的系统上安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不成功，启动或可能无法正常工作。  
  
 **原因**  
  
 UAC 时运行的应用程序被标记为特定的权限级别，如果所需的级别高于运行该应用程序的用户的将显示一个提示，您可以暂时提升到应用程序的权限所需的级别。 随附的工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不具有正确的标志来自动请求权限提升，因此该工具将尝试在运行该应用程序的用户当前的权限级别运行和更高的特权级别时将失败必填。  
  
 **解决方法**  
  
 若要解决此问题，请使用管理权限运行所有 BizTalk Server 工具。 要使用管理权限运行工具，用鼠标右键单击该应用程序，然后选择**以管理员身份运行**。  
  
 有关用户帐户控制的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=99167 ](http://go.microsoft.com/fwlink/?LinkId=99167)。  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a>有时 BizTalk 映射器工具箱可能显示为空  
 **问题**  
  
 有时，当在 Visual Studio 中打开映射器工具箱，看不在工具箱中的所有 functoid。  
  
 **原因**  
  
 可能是有可能损坏的安装/卸载 Visual Studio 加载项和/或损坏。  
  
 **解决方法**  
  
 解决此问题：  
  
1.  关闭所有正在运行的 Visual Studio 实例。  
  
2.  启动**Visual Studio 命令提示符**以管理员身份。  
  
3.  在命令提示符下，键入以下命令：  
  
    ```  
    devenv.exe /setup  
    ```