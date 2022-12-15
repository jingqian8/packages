In hcidump tool, when dumping frame type HCI_EVENT_PKT, event EVT_LE_META_EVENT, we noticed the hcidump crash because of the subevent greater than LE_EV_NUM:
   printf("%s\n", ev_le_meta_str[subevent];

This patch added the range check for subevent, and print the event defined in ev_le_meta_str only when it's within the range.
