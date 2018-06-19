---
title: BizTalk ESB 工具包示例应用程序 |Microsoft 文档
description: 安装 ESB 工具包示例应用程序，并获取有关如何在 BizTalk Server 中使用它们快速链接
caps.latest.revision: 5
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: f9d1af5c2bc8c16ec14f8e13109f0edfe13b86cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290685"
---
# <a name="biztalk-esb-toolkit-sample-applications"></a>BizTalk ESB 工具包示例应用程序
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括几个示例应用程序可以安装和运行，以查看如何 ESB 工作原理以及如何使用某些 ESB 管道组件。 您可以调整和修改的代码和在这些示例用于自己的应用程序的技术。  
  
## <a name="install-the-sample-applications"></a>安装示例应用程序  
  
1.  创建一个名为 c： 驱动器的根目录中的项目文件夹并创建名 Microsoft.Practices.ESB 为在此文件夹的子文件夹。  
  
    > [!NOTE]
    >  在当前版本中，支持的安装为要驻留在 C:\Projects\Microsoft.Practices.ESB 文件夹中的文件。 这些示例会随附的 BizTalk 绑定文件取决于此路径。  
  
2.  当你安装[ESB 工具包](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)，它包括在你指定的安装位置中调用 ESBSource.zip 的.zip 文件 (默认情况下，C:\Program Files\\[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)])。 将 ESBSource.zip 文件解压缩到 C:\Projects\Microsoft.Practices.ESB 文件夹。 这将创建名为的文件夹**密钥**和**源**包含示例密钥和与源代码示例。 源文件夹包含示例应用程序的源代码，密钥文件夹包含用于对示例应用程序中的程序集进行签名的公钥。  
  
3.  运行示例之前，删除 C:\Projects\Microsoft.Practices.ESB\ 文件夹的只读特性，以便正确安装这些示例。  
  
4.  如果你不使用 PowerShell 脚本之前，必须以管理员身份打开 PowerShell 并运行以下命令：  
  
    ```  
    set-executionpolicy unrestricted  
    ```  
  
    > [!NOTE]
    >  有关 PowerShell 的详细信息，请参阅[Windows PowerShell 博客](http://go.microsoft.com/fwlink/?LinkId=187593)([http://go.microsoft.com/fwlink/?LinkId = 187593](http://go.microsoft.com/fwlink/?LinkId=187593)) 和[Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId = 187594](http://go.microsoft.com/fwlink/?LinkId=187594)) MSDN 上。  
  
5.  打开管理员命令提示符并运行以下命令以确保注册 WCF 脚本映射：  
  
    ```  
    C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
    ```  
  
> [!NOTE]
>  你需要以获取对示例代码的访问权限打开 ESBSource.zip 文件。  

## <a name="sample-applications"></a>示例应用程序  
 以下主题描述了示例应用程序，并包括其他安装说明 （如果适用）：  
  
-   [安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [运行修复并重新提交自定义异常处理程序示例](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [运行保留自定义异常处理程序的示例消息](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [运行 BizTalk 失败消息路由 ESB 处理示例](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [安装和运行 JMS MQRFH2 组件示例](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [安装和运行 Namespace 组件示例](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [安装和运行转换服务示例](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [安装和运行 BizTalk 操作示例](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [安装和运行解析程序服务示例](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [安装和运行消息扩充示例](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [安装和运行设计器扩展性示例](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [运行的异常处理服务示例](../esb-toolkit/running-the-exception-handling-service-sample.md)