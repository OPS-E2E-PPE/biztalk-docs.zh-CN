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
# <a name="install-the-jms-mqrfh2-sample-using-the-install-scripts"></a><span data-ttu-id="513ec-102">安装 JMS MQRFH2 示例使用安装脚本</span><span class="sxs-lookup"><span data-stu-id="513ec-102">Install the JMS MQRFH2 Sample Using the Install Scripts</span></span>
<span data-ttu-id="513ec-103">本部分介绍如何安装 JMS MQRFH2 示例使用提供的安装脚本[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="513ec-103">This section describes how you can install the JMS MQRFH2 sample using the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="513ec-104">**若要从安装脚本安装 JMS MQRFH2 示例**</span><span class="sxs-lookup"><span data-stu-id="513ec-104">**To install the JMS MQRFH2 samples from the install scripts**</span></span>  
  
1.  <span data-ttu-id="513ec-105">使用 WebSphere 资源管理器使用的名称创建一个队列管理器**ESB。JMS。Sample.QueueManager**。</span><span class="sxs-lookup"><span data-stu-id="513ec-105">Using WebSphere Explorer, create a Queue Manager with the name **ESB.JMS.Sample.QueueManager**.</span></span>  
  
2.  <span data-ttu-id="513ec-106">使用 WebSphere 资源管理器，创建以下四个队列中的**ESB。JMS。Sample.QueueManager:**</span><span class="sxs-lookup"><span data-stu-id="513ec-106">Using WebSphere Explorer, create the following four queues within **ESB.JMS.Sample.QueueManager:**</span></span>  
  
    -   <span data-ttu-id="513ec-107">ESB.JMS.SAMPLE.DYNAMICQ1</span><span class="sxs-lookup"><span data-stu-id="513ec-107">ESB.JMS.SAMPLE.DYNAMICQ1</span></span>  
  
    -   <span data-ttu-id="513ec-108">ESB.JMS.SAMPLE.DYNAMICQ2</span><span class="sxs-lookup"><span data-stu-id="513ec-108">ESB.JMS.SAMPLE.DYNAMICQ2</span></span>  
  
    -   <span data-ttu-id="513ec-109">ESB。JMS。示例。回复</span><span class="sxs-lookup"><span data-stu-id="513ec-109">ESB.JMS.SAMPLE.REPLY</span></span>  
  
    -   <span data-ttu-id="513ec-110">ESB。JMS。示例。SENDTOBIZTALK</span><span class="sxs-lookup"><span data-stu-id="513ec-110">ESB.JMS.SAMPLE.SENDTOBIZTALK</span></span>  
  
3.  <span data-ttu-id="513ec-111">在 **“开始”** 菜单上，单击 **“运行”** 。</span><span class="sxs-lookup"><span data-stu-id="513ec-111">On the **Start** menu, click **Run**.</span></span>  
  
4.  <span data-ttu-id="513ec-112">在中**运行**对话框中，键入**cmd**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="513ec-112">In the **Run** dialog box, type **cmd**, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="513ec-113">运行以下命令，替换 *\<路径\>* 参数替换为你想要安装的.cmd 文件的完整路径 (在此版本中的默认路径是 \Source\Samples\JMS\Install\Scripts\\):</span><span class="sxs-lookup"><span data-stu-id="513ec-113">Run the following command, replacing the *\<path\>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\JMS\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```