---
title: 部署使用 WCF LOB 适配器 SDK 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 376b4dcf-2d2c-4872-a394-67edc0c3d088
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c11ae1067fff276d8d24639d3e4d3cc6798c6ba5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967291"
---
# <a name="deploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a>部署使用 WCF LOB 适配器 SDK 的适配器
若要部署的适配器，必须将适配器程序集安装到全局程序集缓存 (GAC) 中，然后 machine.config 文件中注册该适配器。  
  
## <a name="install-the-adapter-assembly-into-the-gac"></a>将适配器程序集安装到 gac 中  
 使用 Visual Studio 中使用的适配器之前[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]命令或在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]功能，你必须安装到 GAC 的程序集。 只有具有强名称的程序集才可安装到 GAC。  
  
> [!NOTE]
>  若要完成此过程，必须在 GAC 上具有写入权限的帐户登录。 本地计算机的管理员帐户拥有这些权限。  
  
#### <a name="configure-a-strong-name-assembly-key-file"></a>配置一个强名称程序集密钥文件  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，加载需要强名称的适配器项目文件。  
  
2.  打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。  
  
3.  在命令提示符下，从你要存储密钥文件的文件夹，键入以下命令，然后按 Enter 键：  
  
     **sn /k***file_name* **.snk**   
  
     示例： **sn /k EchoAdapter.snk**  
  
     一条确认消息，**密钥对写入到** \< *file_name*\>**.snk** `,`显示命令行上。  
  
4.  在 Visual Studio 解决方案资源管理器，右键单击该项目，然后单击**属性**。  
  
5.  在左窗格中，展开**通用属性**，然后单击**程序集**。  
  
6.  在右窗格中，向下滚动到**强名称**框。  
  
7.  在**强名称**框中，单击该字段旁边**程序集密钥文件**，单击浏览按钮 (**...**)，然后浏览到该密钥文件。  
  
8.  单击密钥文件，然后单击**打开**，然后单击**确定**。  
  
9. 在 Visual Studio 菜单上，单击**生成**，然后选择**生成解决方案**。  
  
> [!NOTE]
>  如果适配器程序集依赖于任何其他程序集，确保这些引用的程序集进行签名的强名称;否则，你将收到错误。  
  
 如果你有源，则可以重新编译具有强名称中，如前面所示。 如果引用程序集属于第三方，则不能确保它将为指定的强名称，可以反汇编，然后重新使用强名称程序集。  
  
 你的原始程序集将被覆盖，因此如果你想要保留原始版本中，请确保你在继续以下步骤之前的备份。  
  
 使用 Microsoft 中间语言 (MSIL) 反汇编程序反汇编程序集：  
  
-   ILDASM thirdparty.dll /out:thirdparty.il  
  
 使用 MSIL 汇编程序重新具有强名称程序集：  
  
-   ILASM thirdparty.il /dll /key=strongkeyfile.snk  
  
#### <a name="install-an-assembly-in-the-gac"></a>安装在 GAC 中的程序集  
  
1.  验证你的适配器已经过签名。  
  
2.  打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。  
  
3.  键入下列命令：  
  
     **gacutil.exe /if"\<**  *的程序集.dll 文件的路径*  **\>"**  
  
4.  此命令将程序集安装到 GAC，覆盖任何具有相同程序集名称的现有程序集。  
  
## <a name="register-the-adapter-in-machineconfig"></a>在 Machine.config 中注册该适配器  
 使用适配器开发[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]呈现为 WCF 绑定。  有关详细信息，请参阅 Microsoft.ServiceModel.Channels.Common.AdapterBinding。  适配器绑定注册 WCF 使用\<bindingExtensions\>节中\<系统。ServiceModel\> ，并使用 WCF 注册适配器传输绑定元素使用\<bindingElementExtensions\>节中\<系统。ServiceModel\>。  
  
 你可以手动编辑使用文本编辑器的 machine.config 文件。  
  
#### <a name="manually-edit-the-machineconfig-file"></a>手动编辑 machine.config 文件  
  
1.  编辑位于 Microsoft .NET 配置文件夹中的 machine.config 文件。 若要执行此操作，请单击**启动**，单击**运行**，类型记事本\<Windows 安装路径\>\Microsoft.NET\Framework\\< 版本\>\CONFIG\machine.config，，然后单击**确定**。  
  
2.  更新 machine.config 文件。 如果文件不包含 system.serviceModel 部分，在末尾的配置文件，但在结束根标记之前添加以下部分。  
  
    > [!NOTE]
    >  适配器的信息中替换"myAdapterBinding"、 版本、 区域性和其他特定于程序集的信息。  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <bindingExtensions>  
            <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
        </bindingExtensions>      <bindingElementExtensions>  
            <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
          </bindingElementExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
     - 或 -  
  
     如果 machine.config 文件包含 system.serviceModel 部分，确定哪些元素缺少，并将它们，添加适配器的信息中替换"MyAdapter"和其他信息。  
  
    ```  
    <extensions>  
      <bindingExtensions>  
            <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
      </bindingExtensions>  
          <bindingElementExtensions>  
            <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
          </bindingElementExtensions>  
    </extensions>  
    ```  
  
3.  关闭并保存 machine.config 文件。  
  
 你还可以使用[服务配置编辑器](https://msdn.microsoft.com/library/ms732009.aspx)修改 machine.config 文件。
  
#### <a name="edit-the-machineconfig-file-using-the-service-configuration-editor"></a>编辑 machine.config 文件使用服务配置编辑器  
  
1.  打开**服务配置编辑器**。 请参阅[服务配置编辑器](https://msdn.microsoft.com/library/ms732009.aspx)有关详细信息。
  
2.  在树视图窗格中 (标记为**配置**)，展开节点树。 单击**高级**文件夹中，单击**扩展**文件夹，，然后选择绑定扩展元素。  
  
     ![服务配置编辑器。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")  
  
3.  创建一个新的绑定扩展。 单击**新建**按钮以打开扩展**配置元素编辑器**对话框。 在**配置名称**，输入所扩展的唯一名称，例如*MyAdapterExtension*。  
  
     ![扩展配置元素编辑器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")  
  
4.  单击**类型**字段，然后再单击省略号按钮 (**...**) 以打开**绑定扩展类型浏览器**对话框。  
  
5.  单击全局程序集缓存 (GAC) 图标，以列出在 gac 中的 Dll。  
  
6.  单击适配器程序集。  
  
     ![生成扩展类型浏览器。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")  
  
7.  单击**打开**按钮以选择该程序集。  
  
8.  在**绑定扩展类型浏览器**对话框框中，单击实现的绑定集合元素的类型名称。  
  
     ![生成扩展类型浏览器。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")  
  
9. 单击**打开**按钮以选择的类型。  
  
10. 单击**确定**关闭**扩展配置元素编辑器**对话框。  
  
11. 在详细信息窗格中的**绑定扩展编辑器**，验证是否显示你的绑定扩展。 在下图中，MyAdapterExtension 是突出显示。  
  
     ![将扩展添加与服务配置编辑器。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")  
  
12. 关闭**服务配置编辑器**。  
  
## <a name="see-also"></a>另请参阅  
 [部署使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)