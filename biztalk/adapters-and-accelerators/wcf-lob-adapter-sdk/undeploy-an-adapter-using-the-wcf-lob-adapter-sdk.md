---
title: 取消部署适配器使用 WCF LOB 适配器 SDK |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98f9a124-9e63-4451-af0e-ffee752fbeac
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84932fa0a140df157408ad77d9fc6bec8c0823fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974582"
---
# <a name="undeploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a>取消部署适配器使用 WCF LOB 适配器 SDK
若要取消部署适配器从一台计算机，用户必须执行以下两项任务：  
  
1.  从全局程序集缓存 (GAC) 卸载适配器程序集 （和所有相关程序集）。  
  
2.  在 machine.config 文件中删除适配器绑定和适配器绑定元素。  
  
## <a name="uninstall-an-assembly-from-the-gac"></a>从 GAC 卸载程序集  
  
#### <a name="use-the-windows-interface"></a>使用 Windows 界面  
  
1.  打开 Windows 资源管理器，如下所示： 单击**启动**，指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**.  
  
2.  浏览到 GAC 中，它位于 systemdrive%\Windows\Assembly。  
  
3.  右键单击你的应用程序中包含每个程序集文件中，单击**卸载**，然后单击**是**以确认。  
  
#### <a name="use-the-command-line"></a>使用命令行  
  
1. 打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。  
  
2. 在命令提示符下，键入以下命令：  
  
    **gacutil /u** \<*的完全限定*<em>程序集名称</em>\>  
  
    在此命令中，程序集名称是要从 GAC 卸载程序集的名称。  
  
    下面的示例从 GAC 中移除名为 hello.dll 的程序集。  
  
    `gacutil /u "MyAdapter,Version=1.0.0.0, Culture=neutral, PublicKeyToken=fafafafafafafafa"`
  
## <a name="remove-the-adapter-binding-from-the-machineconfig-file"></a>从 Machine.config 文件中删除适配器绑定  
 可以手动编辑 machine.config 文件来删除适配器绑定，或使用服务配置编辑器。 本部分列出了这两个步骤。 
  
#### <a name="manually-edit-the-machineconfig-file"></a>手动编辑 machine.config 文件  
  
1.  编辑位于 Microsoft .NET 配置文件夹中的 machine.config 文件。 若要执行此操作，请单击**启动**，单击**运行**，类型**记事本\<Windows 安装路径\>\Microsoft.NET\Framework\\< 版本\>\CONFIG\machine.config**，然后单击**确定**。  
  
    > [!NOTE]
    >  在进行更改，以防止受到编辑错误之前请 machine.config 文件的备份。  
  
2.  更新 machine.config 文件。 找到你想要删除的适配器 bindingExtensions 元素。 根据存在的其他信息，执行以下操作：  
  
    -   如果有其他 bindingExtensions，删除你的适配器扩展。  
  
    -   如果不有任何其他 bindingExtensions，您可以删除 bindingExtensions 部分 （包括适配器扩展名）。  
  
    -   如果没有任何其他 bindingExtensions 或扩展，则可以删除扩展部分。  
  
    -   最后，如果 system.serviceModel 包含您的适配器扩展，则可以删除整个 system.serviceModel 节。  
  
3.  BindingElementExtensions 元素重复步骤 2。  
  
4.  关闭并保存 machine.config 文件。  
  
#### <a name="use-the-service-configuration-editor-do-change-the-machineconfig-file"></a>使用服务配置编辑器更改 machine.config 文件  
  
1.  打开服务配置编辑器。 请参阅[服务配置编辑器](https://msdn.microsoft.com/library/ms732009.aspx)有关详细信息。
  
2.  在树视图窗格中 (标记为**配置**)，展开节点树。 单击**高级**文件夹中，单击**扩展**文件夹，，然后选择绑定扩展元素。  
  
3.  在绑定扩展编辑器的详细信息窗格中，单击你想要删除，然后单击该绑定扩展**删除**。 在下图中，MyAdapterExtension 突出显示，并将被删除。  
  
     ![具有添加的扩展的服务配置编辑器。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")  
  
4.  关闭服务配置编辑器。  
  
## <a name="see-also"></a>请参阅  
 [部署适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)