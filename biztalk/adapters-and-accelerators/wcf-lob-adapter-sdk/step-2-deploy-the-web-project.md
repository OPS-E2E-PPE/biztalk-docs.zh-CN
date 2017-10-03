---
title: "步骤 2： 部署 Web 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb775a89-2e2d-43e5-94ae-f75c1756dbd7
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 503ce37fd06f91d5036f08c9eee752017c0ad21c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-deploy-the-web-project"></a>步骤 2： 部署 Web 项目
![步骤 2 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **完成时间：** 5 分钟  
  
 在此步骤中将发布 Web 项目中生成[步骤 1： 使用适配器服务开发向导来创建 Web 项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)到 Internet 信息服务 (IIS)。  
  
## <a name="prerequisites"></a>先决条件  
 若要完成此步骤，你应该先完成[步骤 1： 使用适配器服务开发向导来创建 Web 项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)。 你的 Web 服务器还必须安装以启用 HTTPS 通信的 SSL 证书。  
  
### <a name="to-compile-and-deploy-the-web-project"></a>若要编译和部署 Web 项目  
  
1.  在[!INCLUDE[vs2010](../../includes/vs2010-md.md)]，加载以前创建的 EchoWeb 项目。  
  
2.  打开[!INCLUDE[vs2010](../../includes/vs2010-md.md)]命令提示符。  
  
3.  在命令提示符下从 C:\tutorials\echoweb 文件夹中，键入以下命令，，然后按 ENTER:  
  
     **sn /k EchoWebKey.snk**  
  
     一条确认消息，**密钥对写入到 EchoWebKey.snk**，显示在命令行上。  
  
4.  关闭命令提示符。  
  
5.  在**解决方案资源管理器**，右键单击 EchoWeb 项目，然后选择**发布网站**。  
  
6.  在**发布网站**对话框中，为**目标位置**，输入**http://machinename/EchoWeb**。 选择**允许可更新此预编译的网站**，**使用固定命名和单个页程序集**，和**启用强命名在预编译的程序集**。 在**密钥文件位置**字段中，单击省略号**（...）**按钮，选择以前，创建的 EchoWebKey.snk 文件，然后单击**确定**。  
  
7.  要验证是否已正确创建网站，请启动 Internet Explorer 中，输入**超链接"http://localhost/EchoWeb/EchoOutboundContract.svc"http://localhost/EchoWeb/EchoOutboundContract.svc**在地址栏中，和然后按 ENTER。 应显示的 Web 页面，介绍 EchoOutboundContractClient。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 你只是你的 Web 项目发布到 IIS。  
  
## <a name="next-steps"></a>后续步骤  
 现在，你已编译并部署项目，则可以转到[步骤 3： 创建应用程序定义文件](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)  
  
## <a name="see-also"></a>另请参阅  
 [教程 3： 承载在 IIS 中的 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)