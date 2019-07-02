---
title: 安装 JMS MQRFH2 示例使用安装脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 785f3e32-83b4-406a-af1b-9499115fbb8f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dfde04d2f4b9faebabbac102f938839596540af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399886"
---
# <a name="install-the-jms-mqrfh2-sample-using-the-install-scripts"></a>安装 JMS MQRFH2 示例使用安装脚本
本部分介绍如何安装 JMS MQRFH2 示例使用提供的安装脚本[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 **若要从安装脚本安装 JMS MQRFH2 示例**  
  
1.  使用 WebSphere 资源管理器使用的名称创建一个队列管理器**ESB。JMS。Sample.QueueManager**。  
  
2.  使用 WebSphere 资源管理器，创建以下四个队列中的**ESB。JMS。Sample.QueueManager:**  
  
    -   ESB.JMS.SAMPLE.DYNAMICQ1  
  
    -   ESB.JMS.SAMPLE.DYNAMICQ2  
  
    -   ESB。JMS。示例。回复  
  
    -   ESB。JMS。示例。SENDTOBIZTALK  
  
3.  在 **“开始”** 菜单上，单击 **“运行”** 。  
  
4.  在中**运行**对话框中，键入**cmd**，然后按 ENTER。  
  
5.  运行以下命令，替换 *\<路径\>* 参数替换为你想要安装的.cmd 文件的完整路径 (在此版本中的默认路径是 \Source\Samples\JMS\Install\Scripts\\):  
  
    ```  
    <path>\Setup_bin.cmd  
    ```