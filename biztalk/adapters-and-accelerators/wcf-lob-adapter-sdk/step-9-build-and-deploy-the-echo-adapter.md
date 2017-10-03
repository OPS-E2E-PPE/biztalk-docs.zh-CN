---
title: "步骤 9： 生成并部署 Echo 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ead10ab-1acf-47c5-ad16-dc6938601906
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cec35363cca2f20b38e8a2ecf8bdaf36306f6554
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a>步骤 9： 生成并部署 Echo 适配器
![步骤 9 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 **完成时间：** 10 分钟  
  
 在此步骤中，你将执行部署 Echo 适配器所需的任务。 这包括如下：  
  
-   创建一个强名称文件并将其分配给 Echo 适配器程序集  
  
-   生成 Echo 适配器  
  
-   发布到 GAC 的程序集  
  
-   注册的 Echo 适配器[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]  
  
## <a name="prerequisites"></a>先决条件  
 若要成功完成此步骤，你应熟悉强名称的文件和 gac。 基本了解[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]配置是有用的但并不是必需。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>指定程序集的强名称  
  
1.  在解决方案资源管理器，右键单击**EchoAdapter**项目，，然后单击**属性**。  
  
2.  在 EchoAdapter 属性页对话框中，选择**签名**从左窗格。  
  
3.  单击**对程序集签名**选项卡。  
  
4.  选择**\<新建 … >**强名称的文件。 当系统提示输入文件的名称，键入**EchoAdapter.snk**，取消保护选择密钥文件使用密码选项，然后单击**确定**。  
  
5.  单击**应用程序**选项卡。  
  
6.  程序集名称更改为**Microsoft.Adapters.Samples.EchoV2**。  
  
7.  单击**文件**在 Visual Studio 菜单然后选择**保存所有**。  
  
### <a name="to-build-and-deploy-echo-adapter"></a>若要生成和部署 Echo 适配器  
  
1.  在解决方案资源管理器，右键单击**EchoAdapter**项目，，然后单击**生成**。 如果生成未成功，则修复任何错误，并请尝试重新生成 Echo 适配器。  
  
2.  打开 Visual Studio 命令提示符。  
  
3.  键入下列命令：  
  
     **gacutil.exe /if"\<**  *路径 assembly\Microsoft.Adapters.Samples.EchoV2.dll* **>"**  
  
     此命令将程序集安装到 GAC，覆盖任何具有相同程序集名称的现有程序集。  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a>若要注册 Windows Communication Foundation Echo 适配器  
  
1.  编辑位于 Microsoft .NET 配置文件夹中的 machine.config 文件。 若要执行此操作，请单击**启动**，单击**运行**，类型**记事本\<Windows 安装路径 > \Microsoft.NET\Framework\\< 版本\>\CONFIG\machine.config**，然后单击**确定**。  
  
2.  更新 machine.config 文件。 如果你 machine.config 不包含 system.serviceModel 部分，在末尾的配置文件，但在结束根标记之前添加以下部分。  
  
    > [!NOTE]
    >  将替换适配器的信息的版本、 区域性、 公钥标记和其他特定于程序集的信息。  
  
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
  
     如果你 machine.config 包含 system.serviceModel 部分，确定哪些元素缺少，并将其添加。  
  
    > [!NOTE]
    >  将替换适配器的信息的版本、 区域性、 公钥标记和其他特定于程序集的信息。  
  
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
  
3.  保存 machine.config 文件。  
  
## <a name="what-did-i-just-do"></a>未我只需做什么？  
 在此 Echo 适配器本教程的最后一步，你将添加到 Echo 适配器的强名称、 生成和部署适配器，然后修改 Machine.config，包括有关适配器的信息。 此时，Echo 适配器应可供消费应用程序。  
  
## <a name="next-steps"></a>后续步骤  
 本教程已完成。 如果你想要测试的.NET 项目中的 Echo 适配器的功能，请参阅[教程 2： 使用.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 8： 为 Echo 适配器实现同步的入站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)   
 [教程 2： 使用.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)