---
title: "安装 WCF LOB 适配器 SDK |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41b9b34b-3fbb-480f-a335-a218eab33693
caps.latest.revision: "40"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2124425fa97729b1bec692fc1a88e301434c0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-wcf-lob-adapter-sdk"></a>安装 WCF LOB 适配器 SDK
安装和配置[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。 
  
## <a name="requirements"></a>要求 
以下你在其中安装在系统上的组件安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 

> [!NOTE]
> **有关受支持版本的列表**，请参阅： 
> 
> [BizTalk Server 2016 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
> [硬件和软件要求 BizTalk Server 2013 和 2013 R2](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)
 
 | | | 
 | --- | --- |
 | Windows | x86 或 x64 <br/><br/>所需的操作系统资源包括：<br/> <ul><li>支持 OleTx 事务所所需的 Microsoft 分布式事务处理协调器 (MSDTC):</li><li>支持可靠消息传递所需的消息队列 (MSMQ):</li><li>Internet Information Services (IIS): 所需如果你想要承载在 IIS 中的应用程序</li><li>Windows Process Activation Service (WAS): 所需如果你想要承载在 WAS 中的应用程序</li></ul> |
 |Windows Communication Foundation| | 
 | [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] | | 
 | [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] | 如果要生成自定义适配器，或使用开发使用适配器的解决方案生成所需[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] | 如果你使用具有适配器是必需的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  |


  
## <a name="install"></a>Install

> [!IMPORTANT]
> * 关闭 Visual Studio 的所有实例
> * 若要执行**完成**安装程序，请确保在计算机上是否安装了 BizTalk Server。  
  
1.  运行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe**以管理员身份。
  
2.  选择**安装 Microsoft BizTalk 适配器**，然后选择**安装 Microsoft WCF LOB 适配器 SDK**。  
  
3.  上**欢迎**屏幕上，选择**下一步**。  
  
4.  接受许可协议，然后选择“下一步”。  
  
5.  在**选择安装类型**，选择安装类型：  
  
    -   若要安装的公共运行的时和工具，选择**典型**。  
  
    -   若要选择的功能，你想安装并安装位置，选择**自定义**，然后选择你想要安装的功能。  
  
    -   若要安装所有功能，请选择**完成**。  
  
6.  选择“安装”。  
  
## <a name="update-or-remove"></a>更新或删除
  
1.  打开**程序和功能**。 
  
2.  在列表中，选择**Windows Communication Foundation LOB 适配器 SDK**，然后选择**更改**。  
  
3.  上**欢迎**屏幕上，选择**下一步**。  
  
4.  执行以下操作之一：  
  
    -   若要选择你想要安装的组件，选择**更改**。  
  
    -   若要修复最新安装中的错误，选择**修复**。  
  
    -   若要删除[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]从计算机上，选择**删除**。  
  
5.  如果您选择要修改安装：  
  
    1.  选择“下一步” 。  
  
    2.  选择**更改**，然后选择**完成**。  
  
6.  如果你选择在修复安装，**准备好修复 WCF LOB 适配器 SDK**对话框中，选择**修复**，然后选择**完成**。  
  
7.  如果你选择中删除适配器，**准备好删除 WCF LOB 适配器 SDK**对话框中，选择**删除**，然后选择**完成**。  
  
  
#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a>卸载 WCF LOB 适配器 SDK 后删除自定义适配器  

 如果您已开发使用任何自定义适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，并且已在你的计算机上注册这些适配器，你还必须完成以下过程。  
  
1.  从全局程序集缓存 (GAC) 中删除自定义适配器。  
  
    1.  打开**Visual Studio 命令提示**。  
  
    2.  删除自定义**适配器.dll**从 GAC 使用**命令 gacutil /u**。  
  
2.  删除自定义适配器绑定到 machine.config 中的引用  
  
    1.  转到下的 machine.config 文件\<*系统驱动器*>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  
  
    2.  通过使用文本编辑器中打开该文件。  
  
    3.  元素 bindingExtensions、 客户端和 bindingElementExtensions system.serviceModel\extensions 下的搜索。  
  
    4.  删除与你自定义适配器 WCF 绑定。  
  
## <a name="do-a-silent-installation"></a>执行无提示安装  
 无提示安装非常适合于测试方案或在大型企业部署的一部分。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供命令行参数，你可以使用 AdapterFramework.msi 执行无提示安装。  
 
> [!NOTE]
>  若要执行无提示安装，应是计算机上的管理员。 

  
1.  以管理员身份打开命令提示符。  
  
2.  键入以下命令：
  
    ```  
    AdapterFramework.msi /quiet MUOPTIN=”Yes”  
    ```  
  
    使用下列命令行选项与 AdapterFramework.msi 结合使用：  
  
    * 使用`/quiet`安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]以无提示方式。  
  
    * 使用 MUOPTIN ="Yes"&#124;"否"以指示如果[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]应检查与 Microsoft Update 的更新。  
    
        当设置为 Yes，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]检查通过 Microsoft 更新的更新。 当设置为 no[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不会检查与 Microsoft Update 的更新。  
  
> [!NOTE]
>  若要显示的命令行安装其他选项，请键入`AdapterFramework.msi /?`在命令提示符。  
  
