---
title: 第 1 步：生成和部署 vPrev BizTalk 项目来接收 IDOC |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, building and deploying previous version of BizTalk project for receiving an IDOC
- migrating, building and deploying previous version of BizTalk project for receiving an IDOC
- migration
ms.assetid: ab6bdf9a-dca5-4acd-97b2-a9afe9792978
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff4cd20f579c41b3bcba504c527e20ae6ba3314
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372854"
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc"></a>第 1 步：生成和部署 vPrev BizTalk 项目来接收 IDOC
![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，您可以生成和部署现有 vPrev BizTalk 项目以接收来自 SAP 系统。  
  
> [!NOTE]
>  不需要对 vPrev BizTalk 项目进行任何更改。  
  
## <a name="prerequisites"></a>先决条件  
 必须具有从 SAP 系统接收 IDOC ORDERS03 vPrev BizTalk 项目。  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a>若要生成和部署 vPrev BizTalk 项目  
  
1.  创建构建和部署解决方案需要一个强名称密钥文件。 若要创建一个强名称密钥文件，请执行以下操作：  
  
    1.  启动 Visual Studio 命令提示符。  
  
    2.  在命令提示符处导航到你想要创建的密钥文件的文件夹。 例如，键入**cd C:\Sample**，然后按 ENTER。  
  
    3.  在命令提示符处，键入**sn-k\<密钥文件名称\>.snk**，然后按 ENTER。  
  
2.  右键单击解决方案资源管理器中的 BizTalk 解决方案名称，然后单击**属性**。 在中**属性页**对话框框中，执行以下操作：  
  
    1.  单击**配置属性**的复选框从左窗格中，并确保**构建**并**部署**选择列。  
  
    2.  单击“确定” 。  
  
3.  右键单击解决方案资源管理器中的 BizTalk 项目，然后单击**属性**。 在中**属性页**对话框框中，执行以下操作：  
  
    1.  在左窗格中，展开**通用属性**，然后单击程序集。  
  
    2.  在右窗格中下,**强名称**类别中，对于**程序集密钥文件**属性，提供前面创建的程序集密钥文件的路径。  
  
    3.  单击“确定” 。  
  
4.  在解决方案资源管理器，右键单击解决方案名称，然后单击**生成解决方案**。  
  
5.  已成功生成解决方案后，右键单击解决方案名称，然后依次**部署解决方案**。  
  
## <a name="next-steps"></a>后续步骤  
 创建和配置 WCF 自定义接收端口，并将其配置为接收来自 SAP 系统使用基于 WCF 的 Idoc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，如中所述[步骤 2:配置 WCF 自定义单向接收端口](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 4：迁移 SAP 接收 IDOC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)