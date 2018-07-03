---
title: 步骤 1： 部署项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0467c140-1f4c-4cfa-b46f-dc1d0f8755d4
caps.latest.revision: 44
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b25af8ee1095a5365fabd955f7185acbc79254db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007550"
---
# <a name="step-1-deploy-the-projects"></a>步骤 1：部署项目
![3 的第 1 步](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：** 在此步骤中，部署了 EAISchemas 和 EAIOrchestration 项目。  
  
 **目的：** 时部署项目或解决方案在 Visual Studio 中的，程序集是自动生成并部署到指定的应用程序。 在此过程中，程序集连同它所包含的业务流程、架构和映射（称为“项目”）将导入本地 BizTalk 管理数据库，并在该数据库中与指定的应用程序建立关联。  
  
## <a name="prerequisites"></a>必要條件  
  
- [第 1 课：定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md)  
  
- [第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)  
  
- 以的成员身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组

- 使用管理权限运行 Visual Studio

> [!TIP]
> 您可以下载所需的教程文件位于[教程 1： 企业应用程序集成](https://www.microsoft.com/download/details.aspx?id=22793)。

## <a name="open-the-solution-with-administrative-rights"></a>使用管理权限打开的解决方案  
  
1. BizTalk Server Administrators 组的成员身份登录到 Windows。  
  
2. 启动**Microsoft Visual Studio**以管理员身份。  
  
3. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**打开**，然后单击**项目/解决方案**。  
  
4. 在中**打开项目**对话框中，浏览到**EAISolution.sln**项目解决方案文件，然后单击**打开**。  
  
   部署过程要求程序集是强签名的。  必须通过将该项目与一个强名称程序集密钥文件相关联来签名你的程序集。  此文件包含在教程文件中。  
  
   BizTalk 应用程序是 BizTalk Server 的一项功能，可使你更快、更轻松地对 BizTalk Server 业务解决方案进行部署、管理和故障排除。 BizTalk 应用程序是 BizTalk Server 业务解决方案中使用的项（称为“项目”）的逻辑分组。 可为项目指定应用程序名。  部署过程会自动创建新的应用程序如果不存在具有指定的名称。  
  
## <a name="configure-and-deploy-the-projects"></a>配置和部署项目  
  
1.  在解决方案资源管理器中右键单击**EAISchemas**项目，并单击**属性**。  
  
2.  单击**签名**选项卡上，选择**程序集签名**。  
  
3.  从下拉列表中**选择强名称密钥文件**框中，选择**\<浏览...\>**.  
  
4.  在中**选择文件**对话框框中，导航到**C:\BTStutorials**，单击**btsTutorials.snk**，然后单击**打开**。 
  
5.  单击**部署**选项卡上，在右侧的框中**应用程序名称**，类型`EAISolution`。  
  
6.  从下拉列表右侧的框中**重新部署**，选择**True**。  
  
7.  在解决方案资源管理器中右键单击**EAISchemas**，然后单击**部署**。  “输出”窗口应显示：  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  重复步骤 1 至 7 以部署 EAIOrchestration 项目。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，你已部署了 EAISchemas 和 EAIOrchestration 项目。  
  
## <a name="next-steps"></a>后续步骤  
 创建物理端口，然后将其绑定到业务流程的逻辑端口。  
  
 [步骤 2： 配置并启动应用程序](../core/step-2-configure-and-start-the-application1.md)   
 [步骤 3：测试解决方案](../core/step-3-test-the-solution2.md)
