---
title: 安装动态解析示例使用安装脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 644b6403-9883-4256-80d5-37881a87ed0e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a2ecbfcf38046a9ad9f4ca2fa7c360f2f5b50a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400308"
---
# <a name="install-the-dynamic-resolution-sample-using-the-install-scripts"></a>安装动态解析示例使用安装脚本
本部分介绍如何从提供的安装脚本安装动态解析示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 **若要从安装脚本安装动态解析示例**  
  
1.  如果你想要执行使用 FTP 的单向消息传送示例，创建以下 FTP 站点：  
  
    -   FTP 虚拟目录名称：扩展  
  
    -   Location: \Source\Samples\DynamicResolution\Test\FTP\Out  
  
    -   权限：读取和写入  
  
    -   确保 BizTalk Application Users 组具有此位置的完全访问权限  
  
2.  如果你想要执行使用 MQSeries 的双向消息传送示例，使用 WebSphere 资源管理器中创建以下：  
  
    -   具有名称 ESB 队列管理器。DEP。Sample.QueueManager  
  
    -   队列名为 TEST。带内 ESB。DEP。Sample.QueueManager  
  
3.  在 **“开始”** 菜单上，单击 **“运行”**。  
  
4.  在中**运行**对话框中，键入**cmd**，然后按 ENTER 以打开命令提示符。  
  
5.  运行以下命令，替换\<路径\>参数替换为你想要安装的.cmd 文件的完整路径 (在此版本中的默认路径是 \Source\Samples\DynamicResolution\Install\Scripts\\):  
  
    ```  
    <path>\Setup_bin.cmd  
    ```