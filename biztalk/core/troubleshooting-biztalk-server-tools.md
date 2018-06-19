---
title: 故障排除 BizTalk Server 工具 |Microsoft 文档
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
ms.openlocfilehash: 5b7aedd8977042d15176781b0595bd5bb225a2fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279765"
---
# <a name="troubleshooting-biztalk-server-tools"></a>BizTalk Server 工具问题疑难解答
本主题集中提供了有关使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包含的工具时遇到的常见问题的信息。  
  
## <a name="known-issues"></a>已知问题  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a>BizTalk Server 工具和实用程序在支持 UAC 的 Windows 系统上可能无法正确工作  
 **问题**  
  
 当在支持用户帐户控制 (UAC) 的系统上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中包含的工具可能无法正常启动或正常工作。  
  
 **可能的原因**  
  
 运行被标记为具有特定权限级别的应用程序时，如果要求的级别高于运行应用程序的用户的级别，则 UAC 将提示你暂时将应用程序的权限提升为所需的级别。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 随附的工具没有用来自动请求权限提升的正确标记，因此该工具将尝试使用运行应用程序的用户的当前权限级别运行，如果要求使用更高级别，则此工具将无法运行。  
  
 **解决方法**  
  
 若要解决此问题，请使用管理权限运行所有 BizTalk Server 工具。 要使用管理权限运行工具，请右键单击应用程序，然后选择**以管理员身份运行**。  
  
 有关用户帐户控制的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167)。  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a>有时 BizTalk 映射器工具箱可能会显示为空白  
 **问题**  
  
 有时，当你打开 Visual Studio 中的映射器工具箱时，会看到工具箱中没有任何 functoid。  
  
 **可能的原因**  
  
 可能是由于安装/卸载 Visual Studio 加载项和/或路径造成的损坏。  
  
 **解决方法**  
  
 解决此问题：  
  
1.  关闭所有运行的 Visual Studio 实例。  
  
2.  启动**Visual Studio 命令提示符**以管理员身份。  
  
3.  在命令提示符下，键入以下命令：  
  
    ```  
    devenv.exe /setup  
    ```