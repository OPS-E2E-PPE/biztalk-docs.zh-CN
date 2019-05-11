---
title: 如何配置已安装的 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, configuring
- deploying, Web services
- Web services, deploying
ms.assetid: 5a281daa-9e1c-47b0-9002-66ea18ed6caf
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 096e21d2d7449e27f407bf7b286174c9ecb9cc34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340806"
---
# <a name="how-to-configure-the-installed-web-service"></a><span data-ttu-id="4b21d-102">如何配置已安装的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="4b21d-102">How to Configure the Installed Web Service</span></span>
<span data-ttu-id="4b21d-103">安装 Web 服务文件后，必须配置 BizTalk Server 以便接收来自 Web 服务的消息。</span><span class="sxs-lookup"><span data-stu-id="4b21d-103">After you install the Web service files, you must configure BizTalk Server to receive messages from the Web service.</span></span>  
  
### <a name="to-configure-the-web-service"></a><span data-ttu-id="4b21d-104">若要配置 Web 服务</span><span class="sxs-lookup"><span data-stu-id="4b21d-104">To configure the Web service</span></span>  
  
1.  <span data-ttu-id="4b21d-105">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后右键单击你想要配置 Web 服务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b21d-105">In BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then right-click the application that you want to configure the Web Service.</span></span>  
  
2.  <span data-ttu-id="4b21d-106">指向**导入**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="4b21d-106">Point to **Import**, and then click **Bindings**.</span></span>  
  
3.  <span data-ttu-id="4b21d-107">在分发文件夹中，选择 BindingInfo.xml 文件，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4b21d-107">Select the BindingInfo.xml file in the distribution folder, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="4b21d-108">启动业务流程并启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="4b21d-108">Start your orchestrations and enable receive locations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b21d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b21d-109">See Also</span></span>  
 <span data-ttu-id="4b21d-110">[如何将绑定导入 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="4b21d-110">[How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="4b21d-111">在无 Visual Studio 的计算机上部署已发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="4b21d-111">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)