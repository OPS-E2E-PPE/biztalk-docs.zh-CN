---
title: 安装 WCF LOB 适配器 SDK |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41b9b34b-3fbb-480f-a335-a218eab33693
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0987052ec5c29b321fdef8ec82a57ab582950dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363643"
---
# <a name="install-the-wcf-lob-adapter-sdk"></a>安装 WCF LOB 适配器 SDK
安装和配置[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。 

## <a name="requirements"></a>要求 
安装以下组件安装在系统上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 

> [!NOTE]
> **有关支持的版本的列表**，请参阅： 
> 
> [硬件和软件要求适用于 BizTalk Server 2016](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
> [BizTalk Server 2013 和 2013 R2 的硬件和软件要求](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)

|                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                         Windows                                          | x86 或 x64 <br/><br/>所需的 OS 资源包括：<br/> <ul><li>Microsoft 分布式事务处理协调器 (MSDTC):支持 OleTx 事务所需</li><li>消息队列 (MSMQ):支持可靠消息传递所需</li><li>Internet 信息服务 (IIS):如果你想要托管在 IIS 中的应用程序所需</li><li>Windows 进程激活服务 (WAS):如果你想要承载在 WAS 中的应用程序所需</li></ul> |
|                             Windows Communication Foundation                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|        [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]        |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|       [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]       |                                                                                                                                     如果要构建自定义适配器，或使用开发使用适配器的解决方案生成所需[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。                                                                                                                                      |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] |                                                                                                                                                                 如果在使用与适配器需要[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。                                                                                                                                                                 |

## <a name="install"></a>安装

> [!IMPORTANT]
> * 关闭 Visual Studio 的所有实例
> * 若要执行操作**完成**设置，请确保在计算机上是否安装了 BizTalk Server。  

1. 运行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe**以管理员身份。

2. 选择**安装 Microsoft BizTalk 适配器**，然后选择**安装 Microsoft WCF LOB 适配器 SDK**。  

3. 上**欢迎**屏幕上，选择**下一步**。  

4. 接受许可协议，然后选择**下一步**。  

5. 在中**选择安装类型**，选择安装类型：  

   -   若要安装的公共运行的时和工具，请选择**典型**。  

   -   若要选择要安装和安装位置的功能，请选择**自定义**，然后选择你想要安装的功能。  

   -   若要安装所有功能，请选择**完成**。  

6. 选择“安装”。  

## <a name="update-or-remove"></a>更新或删除

1. 打开**程序和功能**。 

2. 在列表中，选择**Windows Communication Foundation LOB 适配器 SDK**，然后选择**更改**。  

3. 上**欢迎**屏幕上，选择**下一步**。  

4. 执行以下操作之一：  

   - 若要选择你想要安装的组件，请选择**更改**。  

   - 若要修复最新安装中的错误，请选择**修复**。  

   - 若要删除[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]从计算机上，选择**删除**。  

5. 如果您选择修改安装：  

   1.  选择“**下一步**”。  

   2.  选择**更改**，然后选择**完成**。  

6. 如果您选择中的修复安装，**准备好修复 WCF LOB 适配器 SDK**对话框中，选择**修复**，然后选择**完成**。  

7. 如果您选择要删除适配器，在**准备好删除 WCF LOB 适配器 SDK**对话框中，选择**删除**，然后选择**完成**。  


#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a>在卸载 WCF LOB 适配器 SDK 之后删除自定义适配器  

 如果您已开发使用任何自定义适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，并已在计算机上注册这些适配器，你还必须完成以下过程。  

1.  从全局程序集缓存 (GAC) 中删除自定义适配器。  

    1.  打开**Visual Studio 命令提示符**。  

    2.  删除自定义**适配器.dll**从 GAC 中使用**命令 gacutil /u**。  

2.  删除自定义适配器绑定到从 machine.config 的引用  

    1.  转到下的 machine.config 文件\<*系统驱动器*\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  

    2.  使用文本编辑器打开该文件。  

    3.  元素 bindingExtensions、 客户端和 bindingElementExtensions system.serviceModel\extensions 下的搜索。  

    4.  移除与自定义适配器的 WCF 绑定。  

## <a name="do-a-silent-installation"></a>执行无提示安装  
 无提示安装非常适合于测试方案或大型企业部署的一部分。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 提供命令行参数，您可以使用与 AdapterFramework.msi 执行无提示安装。  

> [!NOTE]
>  若要执行无提示安装，应是计算机上的管理员。 


1. 以管理员身份打开命令提示符。  

2. 键入以下命令：

   ```  
   AdapterFramework.msi /quiet MUOPTIN=”Yes”  
   ```  

   使用下列命令行选项与 AdapterFramework.msi 结合使用：  

   * 使用`/quiet`若要安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]以无提示方式。  

   * 使用 MUOPTIN ="Yes"&#124;"否"以指示如果[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]检查与 Microsoft Update 的更新。  

       当设置为 Yes，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]检查通过 Microsoft Update 的更新。 当设置为 no[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不会检查与 Microsoft Update 的更新。  

> [!NOTE]
>  若要显示的命令行安装的其他选项，请键入`AdapterFramework.msi /?`在命令提示符处。  

