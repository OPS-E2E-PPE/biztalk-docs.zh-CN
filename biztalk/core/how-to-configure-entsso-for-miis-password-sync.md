---
title: 如何配置 ENTSSO 以实现 MIIS 密码同步 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89438935-37c1-4ac9-9ca2-7af8d9bfd3ae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9716e855a6eea34a7f24c534dabd57c8a628c960
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386315"
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a>如何配置 ENTSSO 以实现 MIIS 密码同步
配置 XML 文件和 Microsoft Identity Integration Server (MIIS) 后，剩余的配置步骤需要企业单一登录 (ENTSSO) 系统中的位置。  
  
### <a name="to-allow-password-sync-from-miis"></a>若要允许从 MIIS 密码同步  
  
1.  在企业单一登录，单击**服务器**节点。  
  
2.  右键单击相应的服务器，然后单击**属性**。  
  
3.  单击**密码同步**选项卡。  
  
4.  选择**允许从 MIIS 密码同步**。  
  
5.  单击“确定” 。  
  
### <a name="to-enable-password-sync-on-the-system-level"></a>若要启用系统级别上的密码同步  
  
1. 在企业单一登录，右键单击**系统**节点。  
  
2. 单击 **“属性”**。  
  
    **属性**对话框随即出现。  
  
3. 单击**选项**选项卡。  
  
4. 在中**启用密码同步**字段中，选择**从 Windows 到适配器**。  
  
    **其他配置**  
  
    最后，您必须配置以下项之一：  
  
   - 密码同步适配器接受 Windows 密码同步。  
  
   - 至少一个应用程序上启用直接密码同步。  
  
     有关如何执行此操作的信息，请参阅您的密码同步文档。  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a>若要为 MIIS 密码同步配置 EntSSO MA  
  
1.  在 ENTSSO 管理代理上**属性**页上，单击**配置扩展**。  
  
2.  在中**密码扩展的连接信息**字段中，单击**设置**。  
  
3.  在中**连接到**字段中，输入将接收密码更改的计算机的名称。  
  
     计算机名称必须在域上创建服务的 ENTSSO 服务主体名称 (SPN) 时使用的格式相同。  
  
     例如：  
  
     短格式-SPN = ENTSSO/ABCD1411，则输入 ABCD1411  
  
4.  长格式-SPN = ENTSSO/ABCD1411.CompanyName.com，则输入 ABCD1411.CompanyName.com  
  
### <a name="additional-configuration-steps"></a>其他配置步骤  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft Identity Integration Server**，然后单击**Identity Manager**。  
  
2.  在“工具”  菜单上，单击“选项” 。  
  
3.  选择**启用密码同步**。  
  
4.  在中**查看管理代理**，选择**ADMA**。  
  
5.  在中**操作**窗格中，选择**属性**。  
  
6.  上**属性**页上，选择**配置目录分区**，然后选择**使该分区作为密码同步源**。  
  
7.  单击**目标**，然后选择 ENTSSOMA2 使其能够从 MIIS 接收密码更改。 取消选择 ENTSSOMA。 单击**确定**，然后单击**确定**试。  
  
8.  在中**管理代理**视图中，选择**ENTSSOMA2**。 在右侧窗格中，选择**属性**。 上**属性**页上，单击**配置扩展**。  
  
9. 确认**启用密码管理**已选中，然后单击**设置**。  
  
10. 在中**连接设置**对话框中，指定以下内容：  
  
    -   连接到：INTSVR1.fabrikam.com  
  
    -   用户： fabrikam\ssosvcact  
  
    -   密码： ssosvcact  
  
        > [!NOTE]
        >  该帐户应与在 INTSVR1.fabrikam.com 上配置的 ENTSSO 服务帐户。  
  
11. 单击**确定**，然后单击**确定**试。  
  
12. 也可以禁用 MIIS 密码同步。 若要执行此操作，在**标识管理器**，单击**工具**菜单中，单击**选项**，然后取消选中**启用密码同步**。  
  
     将应用下列限制：  
  
    -   用于密码同步才能正常工作，必须在 ENTSSO 管理代理将与通信的 ENTSSO 服务帐户配置 SPN。  
  
    -   MIIS 和 ENTSSO 服务器之间的通信需要 Kerberos。  
  
13. 在 ENTSSO 管理代理的 MIIS 连接配置中配置密码扩展时, 指定的帐户必须与匹配将从 MIIS 接收密码的 ENTSSO 服务器的服务帐户。  
  
## <a name="see-also"></a>请参阅  
 [如何使用 ENTSSO 管理代理](../core/how-to-use-the-entsso-management-agent.md)