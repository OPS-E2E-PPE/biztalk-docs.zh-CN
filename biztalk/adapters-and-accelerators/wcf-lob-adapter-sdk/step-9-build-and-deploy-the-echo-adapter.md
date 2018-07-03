---
title: 步骤 9： 生成并部署 Echo 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ead10ab-1acf-47c5-ad16-dc6938601906
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58e0bae620c43504091c29ed2b03a33e0c7710c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980502"
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a>步骤 9： 生成并部署 Echo 适配器
![步骤 9 的 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 **完成时间：** 10 分钟  
  
 在此步骤中，将执行部署 Echo 适配器所需的任务。 这涉及到以下所有内容的：  
  
- 创建一个强名称文件并将其分配给 Echo 适配器程序集  
  
- 生成 Echo 适配器  
  
- 发布到 GAC 的程序集  
  
- 注册使用 Echo 适配器 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]  
  
## <a name="prerequisites"></a>必要條件  
 若要成功完成此步骤中，您应熟悉强名称文件和 gac。 基本了解[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]配置是有所帮助，但并不是必需。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>指定程序集的强名称  
  
1.  在解决方案资源管理器中右键单击**EchoAdapter**项目，并单击**属性**。  
  
2.  在 EchoAdapter 属性页对话框中，选择**签名**在左窗格中。  
  
3.  单击**为程序集签名**选项卡。  
  
4.  选择**\<新...\>** 强名称文件。 当系统提示输入文件的名称，键入**EchoAdapter.snk**，取消选择保护密钥文件的密码选项，然后单击**确定**。  
  
5.  单击**应用程序**选项卡。  
  
6.  将程序集名称更改为**Microsoft.Adapters.Samples.EchoV2**。  
  
7.  单击**文件**上的 Visual Studio 菜单然后选择**全部保存**。  
  
### <a name="to-build-and-deploy-echo-adapter"></a>若要生成并部署 Echo 适配器  
  
1.  在解决方案资源管理器中右键单击**EchoAdapter**项目，并单击**生成**。 如果生成不成功，修复所有错误并尝试重新生成 Echo 适配器。  
  
2.  打开 Visual Studio 命令提示符。  
  
3.  键入下列命令：  
  
     **gacutil.exe /if"\<**  *assembly\Microsoft.Adapters.Samples.EchoV2.dll 路径*  **\>"**  
  
     此命令将程序集安装到 GAC，覆盖任何具有相同程序集名称的现有程序集。  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a>若要使用 Windows Communication Foundation 注册 Echo 适配器  
  
1. 编辑位于 Microsoft .NET 配置文件夹中的 machine.config 文件。 若要执行此操作，请单击**启动**，单击**运行**，类型**记事本\<Windows 安装路径\>\Microsoft.NET\Framework\\< 版本\>\CONFIG\machine.config**，然后单击**确定**。  
  
2. 更新 machine.config 文件。 如果在 machine.config 中不包含 system.serviceModel 部分，配置文件，但之前关闭根标记的结尾处添加以下部分。  
  
   > [!NOTE]
   >  版本、 区域性、 公钥标记和其他特定于程序集的信息将替换为您的适配器的信息。  
  
   ```  
   <system.serviceModel>  
     <client>  
       <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
         name="echov2" />  
     </client>  
     <extensions>  
       <bindingElementExtensions>  
         <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
       </bindingElementExtensions>  
       <bindingExtensions>  
         <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
       </bindingExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   - 或 -  
  
     如果您的 machine.config 包含 system.serviceModel 部分，确定哪些元素缺少，并将其添加。  
  
   > [!NOTE]
   >  版本、 区域性、 公钥标记和其他特定于程序集的信息将替换为您的适配器的信息。  
  
   ```  
   <client>  
     <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
       name="echov2" />  
   </client>  
   <extensions>  
     <bindingElementExtensions>  
       <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
     </bindingElementExtensions>  
     <bindingExtensions>  
       <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
     </bindingExtensions>  
   </extensions>  
   ```  
  
3. 保存 machine.config 文件。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在 Echo 适配器教程的此最后一步，您将添加到 Echo 适配器的强名称，生成和部署该适配器，然后修改 Machine.config，包括有关适配器的信息。 此时，Echo 适配器应可供使用方应用程序。  
  
## <a name="next-steps"></a>后续步骤  
 本教程中已完成。 如果你想要在.NET 项目中测试 Echo 适配器的功能，请参阅[教程 2： 使用 Echo 适配器通过.NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 8： 实现 Echo 适配器的同步入站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)   
 [教程 2：从 .NET 使用 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)