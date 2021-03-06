---
title: 如何将 BAM 侦听器行为添加到 Machine.config 文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ea09925-264f-4976-8e34-f63bad70f886
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ef2ac191a50929be06fb5093d93382b63d2959
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387304"
---
# <a name="how-to-add-the-bam-interceptor-behavior-to-the-machineconfig-file"></a>如何将 BAM 侦听器行为添加到 Machine.config 文件
若要截获 BAM 中的数据，必须将 BAM 侦听器行为添加到 Microsoft.NET 的 machine.config 文件中。 可以通过两种方式来执行此操作：  
  
-   手动编辑 machine.config 文件来添加此行为。  
  
-   使用服务配置编辑器来添加此行为。  
  
### <a name="to-manually-edit-the-machineconfig-file"></a>若要手动编辑 machine.config 文件  
  
1.  编辑 machine.config 文件位于 Microsoft.NET 配置文件夹中。 若要执行此操作，请单击**启动**，单击**运行**，键入记事本 c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config，然后单击**确定**。  
  
2.  使用以下行为扩展更新 machine.config 文件。  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="BAMEndPointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
3.  关闭并保存 machine.config 文件。  
  
#### <a name="to-edit-the-machineconfig-file-using-the-service-configuration-editor"></a>若要编辑使用服务配置编辑器的 machine.config 文件  
  
1.  打开服务配置编辑器。 有关使用服务配置编辑器的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=83557 ](http://go.microsoft.com/fwlink/?LinkId=83557)。  
  
2.  在树视图窗格中 (标记为**配置**)，展开节点树。 单击**高级**文件夹中，单击**扩展**文件夹，，然后选择**行为元素扩展**元素。  
  
3.  创建一个新的行为元素扩展。 单击**新建**按钮以打开扩展配置元素编辑器对话框。 在中**配置名称**输入的行为，例如 BAMEndPointBehaviorExtension 的唯一名称。  
  
     ![扩展配置元素编辑器](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")  
  
4.  单击**类型**字段，，然后单击省略号按钮 (**...**) 按钮以打开行为扩展类型浏览器对话框。  
  
5.  单击全局程序集缓存 (GAC) 图标以列出 GAC 中的 Dll。  
  
6.  选择 Microsoft.BizTalk.Bam.Interceptors 程序集。  
  
7.  单击**打开**按钮以选择的程序集，然后关闭对话框。  
  
     ![Bejavopr 扩展类型浏览器](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")  
  
8.  在行为扩展类型浏览器对话框中的类型名称窗格中，双击 Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior 类型 （如以下屏幕中，突出显示部分）。  
  
     ![Bejavopr 扩展类型浏览器](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")  
  
     这将打开扩展配置元素编辑器。  
  
9. 单击**确定**以关闭扩展配置元素编辑器对话框。  
  
10. 在服务配置编辑器的详细信息窗格中，验证 bamendpointbehaviorextension 显示。  
  
11. 关闭服务配置编辑器。  
  
## <a name="next-steps"></a>后续步骤  
 [如何配置 BAM WCF 侦听](../core/how-to-configure-the-bam-wcf-interception.md)  
  
## <a name="see-also"></a>请参阅  
 [配置 WCF 适配器以侦听 BAM 数据](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)