---
title: MIME （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, MIME/SMIME Encoder [pipeline component]
- examples, send pipelines
- MIME/SMIME Encoder [pipeline component], send pipelines
- MIME/SMIME Encoder [pipeline component], examples
- examples, MIME/SMIME Encoder [pipeline component]
ms.assetid: f76c720d-3798-4f15-a5f9-885ddf421d57
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e96e4efd7cb8160871a7fd9d7ac9f1709e0605e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997174"
---
# <a name="mime-biztalk-server-sample"></a>MIME （BizTalk Server 示例）
MIME 示例演示如何在发送管道中执行 MIME 编码。  

## <a name="what-this-sample-does"></a>本示例的用途  
 本示例将 MIMEIn 文件夹配置为接收位置。 在将文件（例如示例文件 ImageInput.gif）放入此文件夹后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将按照以下步骤处理此文件内的消息：  

1.  从接收位置文件夹 MIMEIn 接收消息文件。  

2.  在接收管道中，不做任何改变地传递该消息。  

3.  在 MessageBox 数据库中，将消息路由至发送管道。  

4.  在发送管道中，执行 MIME 编码并将文件放置到发送适配器文件夹 MIMEOut 中。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Pipelines\MIME\  

 下表显示了本示例中的文件及其用途说明：  


|                           文件                            |                                                                                              Description                                                                                               |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                         Cleanup.bat                          | 用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。 |
|                        ImageInput.GIF                        |                                                                                           示例输入文件。                                                                                           |
| SampleMimeEncoding.btproj<br /><br /> SampleMimeEncoding.sln |                                                                              本示例的项目文件和解决方案文件。                                                                               |
|                SampleMimeEncodingBinding.xml                 |                                                                             用于如端口绑定之类的自动化设置。                                                                             |
|                     SendMimePipeline.btp                     |                                 带 MIME 编码器组件的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送管道文件。                                 |
|                          Setup.bat                           |                                                                               用于生成和初始化本示例。                                                                                |

## <a name="building-and-initializing-this-sample"></a>生成并初始化本示例  
 使用以下过程可以生成并初始化 MIME 示例。  

#### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  

1. 在命令窗口中，导航到下面的文件夹：  

    \<*示例路径*\>\Pipelines\MIME  

2. 运行 Setup.bat 文件，该文件将执行以下操作：  

   - 在下面的文件夹中，为本示例创建输入 (MIMEIn) 和输出 (MIMEOut) 文件夹：  

      \<*示例路径*\>\Pipelines\MIME  

   - 编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。  

   - 创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。  

     > [!NOTE]
     >  本示例将显示以下警告时创建并绑定端口：  

     > [!NOTE]
     >  `Warning: Receive handler not specified for receive location "MIMEReceiveLocation"; updating with first receive handler with matching transport type.`  

     > [!NOTE]
     >  可以安全地忽略这些警告。 （若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）  

   - 启用接收位置并启动发送端口。  

> [!NOTE]
>  如果从安装位置以外的位置运行此示例，必须首先添加对的引用**Microsoft.BizTalk.Pipeline.Components**程序集。  
> 
> [!NOTE]
>  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
> 
> [!NOTE]
>  如果你选择打开并生成本示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。 若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 MIME 示例。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1.  将 ImageInput.gif 文件的副本放到 MIMEIn 文件夹中。  

2.  查看在 MIMEOut 文件夹中创建的文本文件。 此文本文件是根据消息 ID GUID 命名的。 此文件包含输入文件 ImageInput.gif 的 MIME 编码的内容。  

## <a name="see-also"></a>请参阅  
 [管道（BizTalk Server 示例文件夹）](../core/pipelines-biztalk-server-samples-folder.md)