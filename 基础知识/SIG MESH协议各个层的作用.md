<!--
 * @Description: In User Settings Edit
 * @Author: ��ʱ��
 * @Date: 2019-08-06 22:05:02
 * @LastEditTime: 2019-12-05 21:36:54
 * @LastEditors: Please set LastEditors
 -->
# ǰ��
������Bluetooth low energy����SIG MESH���غɰ��������ɲ�ͬ��Э�����ϵ��²��ƴװ�������PHY�㽫���ݷ��ͳ�ȥ����ˣ�����Խ�����ζ��Խ���ӡ�����Ϊ��ˣ�������Ҫ���ε��˽�SIG MESH�����Ҫ���˽�SIG MESHЭ��ջ��������ã�ֻ�������������ŪMESH�ڹ���֮�У��������������

# SIG MESH Э���һ��
�����ǿ�ʼ��������������֮ǰ���ȿ�������SIG MESHЭ����ǳ�ʲô���ġ�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/mesh_system_architecture.png)

����ͼ��֪��SIG MESH��**ģ�Ͳ�**��**����ģ�Ͳ�**��**���ʲ�**��**�ϲ㴫���**��**�²㴫���**��**�����**��**���ز�**��ɣ����ʱ����ܶ��߻��ʣ�Ϊʲô**�͹����������Ĺ淶**�������������أ�
> �ڻش��������֮ǰ�������ȿ���Mesh���ݰ��ĸ�ʽ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Mesh_packet.svg?sanitize=true)
�������mesh���ݰ��ķֽ�ͼ���������ʱ���������������Ϊɶ**�͹����������Ĺ淶**�������������˰ɣ�mesh�����ݰ�ʵ�������õ͹��������շ����ݣ�����mesh�����ݰ������ƴװ����ô��װ���Լ��ӽ��ܵȵ��ǲ���meshЭ��ջ�������顣��ˣ�����Ҳ���Լ򵥵�˵meshЭ��ջ����һ������BLE��Big profile�����⣬С��Ҫ�ᵽ���ǣ�**���Ĳ�������ܸ�Ӧ�ò��õ���Ч�غɰ�����11�ֽڣ�����ע�⣬�������ǽ���ָ���ǲ�����ʱ�����PDU��ʵ��һ�ο��Է������380�ֽڵ�mesh���ݣ�����Ҫ�ְ�**

����������ݣ���������Ը��������������һ����ŵ��˽��ˣ�������������ݰ�����⣬���ǻ��ں�����½ڸ���ʵ�ʵİ���׽�����⡣����С��Ͳ��ڴ˴���չ�����½ڵ���Ҫ���ô��֪��meshЭ��ջ�����������ʲô��

## ���ز�
mesh���ݰ����շ�����Ҫý��ģ���������������ǿ���֪�����������˵͹��������������ݵ��շ������ز㶨���˽ڵ�֮������δ���������Ϣ�ģ��䶨�����������أ�
- GATT

    ��ôGATT���ص����õ�����ʲô�أ������ò�֧��meshЭ��ջ���豸��mesh����Ľڵ��ӵؽ���ͨ�ţ���������ͨ��ʲô��ʽ������Ľڵ���н����أ�����ʹ�á�����Э�顱��û������Proxy�ڵ㣬���ǿ���ʵ����ЩGATT���Եģ�����ͬʱ֧��GATT���غ�ADV���� **���е��˿��ܻ���Ϊɶ��Ҫ֧��ADV���أ��ⲻ�Ƿϻ��������֧�ֵĻ���ô�ò�֧��meshЭ����豸�������͵�mesh������ȥ����������Ϊ����mesh�����е������շ�����ͨ��ADV����ʵ�ֵģ�**
    
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/talking_about_proxy_node.gif)
    
    Ҳ����˵֧�ִ���Э��Ľڵ���֧��**mesh proxy service** �Լ��㲥��Ϊ�ģ�Ϊ���ô�Ҹ��õ���⣬���ǿ��Կ�������ʾ������ͼ��
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/mesh_proxy_service.png)

- ADV

    ADV��������BLE��GAP�㲥��ɨ�������ͺͽ�������PDU������ͼ��ʾ��
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/mesh_message_ad_type.png)

## �����
�������SIG MESH����Ҫ����ɲ��֣��书�ܿ��Է�Ϊ���¼������֣�

1. �����˱����ز�ת��ĵײ㴫���PDU������PDU��ʽ���������ܻ��е��ֿڣ���������������½ڵ�Mesh���ݰ��ֽ�ͼ�����������ˡ��ײ㴫��PDU���ϲ�����װ������PDU��Ȼ���ٱ�ת�͵����ز㣻
2. �����ܲ���֤��ת��������ӿڽ��յ���ת�ͽ�������Ϣ���ϲ㴫��㣬�ͻ�������ӿڣ������ܺ���֤��ת���ɷ����������ӿڵ������Ϣ��������߿��ܻ������ʣ�ʲô�ǽӿڣ�����ô������������
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/doubts_emoticon.png)

    ���������뻹������ӿڣ����Ƕ����� **������ӿڡ�**��

    - ����ӿ�
      
      ���������mesh��Ϣ�ɷ�������㻹�Ƕ�������Ҳ����˵������mesh��Ϣת�뵽����㻹��ֱ�Ӷ�������
    - ����ӿ�
      
      ����������mesh��Ϣ�����ز㻹�Ƕ�������ͬʱ������GATT���ػ���ADV���ض�Ҫ��TTL����1��������Ϣȫ������ͬ��Ҳ����˵��������װ�õ��������Ϣ���͵����ز㻹�Ƕ�������

�����ϸ�ĵĶ��߿����Ѿ������**����**�Լ�**�м�**��������������һ����Ϊ��Ҳ����˵������м̵Ĺ�������һ��õ�ʵ�֡���Ϊ��������ݲ��ϵ���ǿ��ת����ת��������ת����ֻ����һ����ͨ��ADV���ؽ�������PDUת��������һ��������GATT��ADV����֮��ת����ǰ�ߵ���Ϊ�����м̣����������Ǵ���

## �ײ㴫���
�������½ڵ�Mesh���ݰ��ֽ�ͼ���Կ������ײ㴫�����ϲ��������ϲ㴫��PDU��Ȼ�������Ϣ���͵��Զ��豸�ĵײ���㣬����Ӧ�����˲�֪��ʲô�ǶԶ��豸�ɣ�
>����A-��B����ô��A���ԣ�B����A�ĶԶ��豸

���ǣ��ϲ㴫����**���ܷ����غɰ�**�����380�ֽڣ����ײ㴫�����Ҫ������ô�����������ô���أ����ʱ��ֻ�ܲ��÷ֶ�����ķ�ʽ�ˡ��������Ҫ���͵�����������11�ֽڣ���ô��ʱ�ͱ���Ҫ�ֶ��ˡ������ڶԶ��豸���ԣ�������յ��Ĳ��Ƿְ����ϲ㴫���PDU�ĵײ㴫��PDU�Ļ������ĵײ㴫�����ֱ�ӰѸ�PDU�����ϲ㴫��㣬������Ҫ����Щ�ְ����ϲ㴫���PDU�ĵײ㴫��PDUs���飬һ�����������ϴ����ϲ㴫��㣻������������������⣬���ǿ��Խ����ͼ�Ϳ��Ժ����������ˡ�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/segmentation_reassembly.png)

��Ȼ���ֻ���ϸ�ĵĶ��߷��֣�ԭ���ֶ��������ڵײ㴫��㴦��ʵ�ֵİ�������������һ�������������ǲ��Ǹо��Լ���mesh�ֶ���һЩ:bowtie:��

## �ϲ㴫���
�ϲ㴫������Ҫְ�����£�

1. �ӷ��ʲ���շ��ʲ��غɰ���ʹ��**application key**������м��ܺ���֤��Ȼ����Щ��Ϣ���͵��Զ��豸���ϲ㴫��㣬���Զ��豸���ϲ㴫��������ͬ��**application key**ȥ��֤���յ�����Ϣ�ĺϷ��ԣ���һ��������Ȼ���Դ������½ڵ�mesh���ݷֽ�ͼ���Կ�����
2. �ڲ����ɵ��ϲ㴫��������Ϣ��ͬ���Ľ������Ϣ���͵��Զ��豸���ϲ㴫��㣻Ȼ����������Ϣ���������㱻��������֤������1��2֮��Ĳ�֮ͬ����

���½ڵ����ݲ��ϵ����ἰ��������Ϣ����ô������Ϣ��ʲô�أ�

| ֵ | ������ | ���� |
|-----|-----|------|
| 0x00 | �C    | Reserved for lower transport layer |
| 0x01 | Friend Poll   | Sent by a Low Power node to its Friend node to request any messages that it has stored for the Low Power node |
| 0x02 | Friend Update   | Sent by a Friend node to a Low Power node to inform it about security updates |
| 0x03 | Friend Request   | Sent by a Low Power node the all-friends fixed group address to start to find a friend |
| 0x04 | Friend Offer   | Sent by a Friend node to a Low Power node to offer to become its friend |
| 0x05 | Friend Clear   | Sent to a Friend node to inform a previous friend of a Low Power node about the removal of a friendship |
| 0x06 | Friend Clear Confirm   | Sent from a previous friend to Friend node to confirm that a prior friend relationship has been removed |
| 0x07 | Friend Subscription List Add   | Sent to a Friend node to add one or more addresses to the Friend Subscription List |
| 0x08 | Friend Subscription List Remove   | Sent to a Friend node to remove one or more addresses from the Friend Subscription List |
| 0x09 | Friend Subscription List Confirm   | Sent by a Friend node to confirm Friend Subscription List updates |
| 0x0A | Heartbeat   | Sent by a node to let other nodes determine topology of a subnet |
| 0x0B~0x7F | RFU   | Reserved for Future Use |

Ϊ�˱�֤ԭ֭ԭζ������ı���ҾͲ������ˣ�������֮�����˼�е㲻̫�Ծ�����û��Ӣ�ı��ĺ���׼ȷ��ͬʱ����Ҳ���ϱ��п�֪��**���Ѻ͵͹���**����ԭ�������ϲ㴫���ʵ�ֵ�,�����һ����Ҫ����---������Ҳ������һ��ʵ�ֵġ�

## ���ʲ�
���ʲ㸺����Ӧ����������ϲ㴫��㣬������
- ����Ӧ�����ݵĸ�ʽ
- ���岢�������ϲ㴫���ִ�еļ��ܺͽ��ܹ���
- �ڽ������ϴ������ߵĲ�֮ǰ���������ϲ㴫��������
������֤���ж����Ƿ������ڸ������Ӧ��

�ò��Ѿ��ǳ��ӽ�Ӧ�ò��ˣ���������һ���ʾ��������Դ��Mesh Model Spec�涨����Щ����ֵ�ˡ�

## ����ģ�Ͳ�
�ò㶨���˷��ʲ��״̬����Ϣ�Լ����ú͹�����״���������ģ�ͣ��������״̬����ϸ��������Mesh spec�Ĳ��֣����ǿ��Դ�**Mesh Model Spec**��ȡ�õ���Щϸ�ڵ����ݣ�ͬ����ض������Ϣ��ϸ��Ҳ�Ǵ�**Mesh Model Spec**�п��Ի�ȡ�õ���Ȼ�������ú͹�����״���������ģ����Ҫ������4����
1. Configuration Server model
2. Configuration Client model
3. Health Server model
4. Health Client model

�����������Щģ�͵���⣬���Ǻ�̻������µ��½�ר�Ž��⣬�˴��򵥵��˽⼴�ɡ�

## ģ�Ͳ�
ģ�Ͳ��漰ģ�͵�ʵʩ������漰һ������ģ�͹�� �ж������Ϊ����Ϣ��״̬��״̬�󶨵ȵ�ʵ�֣��������ϸ�������ǿ��Դ�**Mesh Model Spec**��֪�����ﲻ������С��Ҳ������ȥ��̫��ʱ��ȥ����������������Ӧ��ģ��ʱ����Ӧ�Ĳ��ļ��ɡ�
