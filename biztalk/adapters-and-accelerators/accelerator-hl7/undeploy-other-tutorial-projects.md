---
title: 取消部署其他教程项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fce837f-1853-4d5d-a680-8ae2a974c750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2c014a094acac4e374605cd0ebd9b9c50c9d733
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976278"
---
# <a name="undeploy-other-tutorial-projects"></a>取消部署其他教程项目
当你部署 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 的教程中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在配置数据库 （也称为 BizTalk 管理数据库） 和全局程序集缓存中存储的教程程序集文件。 如果您已运行另一个[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]教程，并已部署在该教程中创建的程序集，您可能会遇到错误时在批处理教程的三个部分中测试您的程序集。 这可能是因为一次只能部署一个消息架构。  
  
 您可以避免这些错误由您在前面的教程中部署的正在取消部署程序集。 如果需要可以重新部署程序集更高版本。  
  
 在取消部署程序集之前，您需要取消登记业务流程的程序集中。 此外需要删除对你想要取消部署，从你想要保留已部署的任何其他程序集的程序集的任何引用。 一种替代方法是删除开始另一个教程前一个教程中，与关联的所有 Dll。  
  
### <a name="to-undeploy-an-assembly"></a>若要取消部署程序集  
  
1. 取消登记业务流程使用在你想要通过单击 BizTalk 浏览器中的 Visual Studio 中的业务流程，然后单击取消部署程序集中**取消登记**。  
  
2. 在你想要保留已部署的任何程序集，删除你想要取消部署的程序集的引用。 右键单击解决方案资源管理器中的引用，然后单击**删除**。  
  
3. 打开 BizTalk 浏览器中，右键单击你想要取消部署，然后单击该程序集**Undeploy**。  
  
   有关取消部署程序集的详细信息，请参阅"正在取消部署程序集使用 BizTalk 浏览器"中 BizTalk Server 帮助。  
  
## <a name="see-also"></a>请参阅  
 [为使用批处理教程做准备](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)