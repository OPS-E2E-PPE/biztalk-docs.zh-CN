---
title: 取消部署其他教程的项目 |Microsoft 文档
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
ms.openlocfilehash: 1e5c4d7e20fc4d8e7c8bea724625dde770b4aca2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006414"
---
# <a name="undeploy-other-tutorial-projects"></a>取消部署其他教程的项目
当为 HL7 部署 BizTalk 快捷键 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 教程，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在配置数据库 （也称为 BizTalk 管理数据库） 和全局程序集缓存中存储的教程的程序集文件。 如果你已运行另一个[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]教程，及已部署在该教程中创建的程序集，你可能会遇到错误时在批处理教程的三个部分中测试你的程序集。 这可能是因为一次只能部署一个消息架构。  
  
 你可以避免这些错误由你在前面的教程中部署的正在取消部署程序集。 如果需要你可以重新部署的程序集更高版本。  
  
 在之前取消部署程序集，你需要取消登记在程序集中的业务流程。 你还需要删除对你想要取消部署，从你想要保留已部署的任何其他程序集的程序集的任何引用。 一种替代方法是删除之前开始另一个教程一个教程中，与关联的所有 Dll。  
  
### <a name="to-undeploy-an-assembly"></a>若要取消部署程序集  
  
1.  取消登记业务流程中你想要通过单击 Visual Studio 中，BizTalk 资源管理器中的业务流程，然后单击取消部署的程序集使用**Unenlist**。  
  
2.  在你想要保留已部署的任何程序集，删除对你想要取消部署的程序集的引用。 右键单击解决方案资源管理器中的引用，然后单击**删除**。  
  
3.  打开 BizTalk 资源管理器中，右键单击你想要取消部署，然后单击该程序集**取消部署后再次**。  
  
 有关取消部署程序集的详细信息，请参阅"正在取消部署程序集使用 BizTalk 资源管理器"BizTalk Server 帮助中。  
  
## <a name="see-also"></a>另请参阅  
 [为使用批处理教程做准备](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)