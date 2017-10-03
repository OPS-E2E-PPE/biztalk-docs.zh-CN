---
title: "如何为 miis 进行密码同步配置 ENTSSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89438935-37c1-4ac9-9ca2-7af8d9bfd3ae
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a1587c2e3c0d2164a7ffd3842b3d74df5b04685
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a>如何配置 ENTSSO 以实现 MIIS 密码同步
配置完 XML 文件和 Microsoft Identity Integration Server (MIIS) 后，其余配置步骤可在企业单一登录 (ENTSSO) 系统中进行。  
  
### <a name="to-allow-password-sync-from-miis"></a>从 MIIS 实现密码同步  
  
1.  在 Enterprise 上单一登录，单击**服务器**节点。  
  
2.  右键单击适当的服务器，然后单击**属性**。  
  
3.  单击**密码同步**选项卡。  
  
4.  选择**允许从 miis 进行密码同步**。  
  
5.  单击 **“确定”**。  
  
### <a name="to-enable-password-sync-on-the-system-level"></a>启用系统级别的密码同步  
  
1.  在 Enterprise 上单一登录，右键单击**系统**节点。  
  
2.  单击 **“属性”**。  
  
     **属性**对话框随即出现。  
  
3.  单击**选项**选项卡。  
  
4.  在**启用密码同步**字段中，选择**从 Windows 到适配器**。  
  
     **其他配置**  
  
     最后，您必须配置以下内容之一：  
  
    -   接受 Windows 密码同步的密码同步适配器。  
  
    -   至少对一个应用程序启用直接密码同步。  
  
     有关如何进行此操作的信息，请参阅“密码同步”文档。  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a>配置 EntSSO MA 以实现 MIIS 密码同步  
  
1.  ENTSSO 管理代理上**属性**页上，单击**配置扩展**。  
  
2.  在**密码扩展的连接信息**字段中，单击**设置**。  
  
3.  在**连接到**字段中，输入将接收密码更改的计算机的名称。  
  
     该计算机名必须采用为该域上的 ENTSSO 服务创建服务主体名称 (SPN) 时所使用的同一格式。  
  
     例如：  
  
     使用短格式 - SPN = ENTSSO/ABCD1411，则输入 ABCD1411  
  
4.  使用长格式 - SPN = ENTSSO/ABCD1411.CompanyName.com，则输入 ABCD1411.CompanyName.com  
  
### <a name="additional-configuration-steps"></a>其他配置步骤  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft Identity Integration Server**，然后单击**Identity Manager**。  
  
2.  在“工具”  菜单上，单击“选项” 。  
  
3.  选择**启用密码同步**。  
  
4.  在**管理代理查看**，选择**ADMA**。  
  
5.  在**操作**窗格中，选择**属性**。  
  
6.  上**属性**页上，选择**配置目录分区**，然后选择**启用密码同步源作为此分区**。  
  
7.  单击**目标**，然后选择 ENTSSOMA2 以使其能够接收从 miis 进行密码更改。 取消选择 ENTSSOMA。 单击**确定**，然后单击**确定**试。  
  
8.  在**管理代理**视图中，选择**ENTSSOMA2**。 在右侧窗格中，选择**属性**。 上**属性**页上，单击**配置扩展**。  
  
9. 确认**启用密码管理**已选择，然后单击**设置**。  
  
10. 在**连接设置**对话框中，指定下列各项：  
  
    -   连接到： INTSVR1.fabrikam.com  
  
    -   用户： fabrikam\ssosvcact  
  
    -   密码： ssosvcact  
  
        > [!NOTE]
        >  该帐户应与在 INTSVR1.fabrikam.com 上配置的 ENTSSO 服务帐户相匹配。  
  
11. 单击**确定**，然后单击**确定**试。  
  
12. 您也可以禁用 MIIS 的密码同步。 为此，请在**Identity Manager**，单击**工具**菜单上，单击**选项**，然后取消选中**启用密码同步**。  
  
     将应用下列限制：  
  
    -   为使“密码同步”功能可以正常工作，必须在作为 ENTSSO 管理代理通信对象的 ENTSSO 服务帐户上对 SPN 进行配置。  
  
    -   MIIS 和 ENTSSO 服务器之间的通信需要 Kerberos。  
  
13. 在 ENTSSO 管理代理的 MIIS 连接配置中配置“密码扩展”时，指定帐户必须与将从 MIIS 接收密码的 ENTSSO 服务器的服务帐户相匹配。  
  
## <a name="see-also"></a>另请参阅  
 [如何使用 ENTSSO 管理代理](../core/how-to-use-the-entsso-management-agent.md)