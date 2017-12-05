---
title: "安装使用安装脚本 JMS MQRFH2 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 785f3e32-83b4-406a-af1b-9499115fbb8f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edb3102fabc84818cb42fcdcba6a034d085bdcc4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="install-the-jms-mqrfh2-sample-using-the-install-scripts"></a>安装使用安装脚本 JMS MQRFH2 示例
本部分介绍如何安装使用提供的安装脚本 JMS MQRFH2 示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 **若要从安装脚本安装 JMS MQRFH2 示例**  
  
1.  使用 WebSphere 资源管理器，创建具有名称的队列管理器**ESB。JMS。Sample.QueueManager**。  
  
2.  使用 WebSphere 资源管理器，创建中的以下四个队列**ESB。JMS。Sample.QueueManager:**  
  
    -   ESB。JMS。示例。DYNAMICQ1  
  
    -   ESB。JMS。示例。DYNAMICQ2  
  
    -   ESB。JMS。示例。答复  
  
    -   ESB。JMS。示例。SENDTOBIZTALK  
  
3.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
4.  在**运行**对话框中，键入**cmd**，然后按 ENTER。  
  
5.  运行以下命令，替换*\<路径\>*参数替换为你想要安装的.cmd 文件的完整路径 (在此版本中的默认路径是 \Source\Samples\JMS\Install\Scripts\\):  
  
    ```  
    <path>\Setup_bin.cmd  
    ```