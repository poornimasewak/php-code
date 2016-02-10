# php-code
code by me
<?php echo $top_header; ?>
    <!-- Top Header Section Ends Here -->
    <link href="<?php echo $css_path; ?>group-options.css" rel="stylesheet" type="text/css"/>
    <script type="text/javascript" src="<?php echo $js_path; ?>group.js"></script>

    <div id="page">
        <!--start page -->

        <!--Logo Header Starts here-->
        <?php echo $logo_header; ?>
        <!--Logo Header Ends here-->

        <!--start content_area -->
        <div class="content_area">

            <!--start left top-->
            <div class="left">
                <!--Left Login Box Starts here-->
                <?php echo $left_login_box; ?>
                <!--Left Login Box Ends here-->
            </div>
            <!--end left top-->

            <!--start right top-->
            <div class="right_top">

                <!--Top Menu Starts here-->
                <?php echo $top_menu; ?>
                <!--Top Menu Ends here-->

                <div class="balance"></div>

                <!--Recently Updated Profile Starts here-->
                <?php echo $recently_updated_profile; ?>
                <!--Recently Updated Profile Ends here-->

            </div>
            <div class="balance"></div>
        </div>
        <!--end content_area  -->

        <!--start left -->
        <div class="left1">
            <!--Left Navigation Starts here-->
            <?php include('left_navigation_create_group.php'); ?>
            <!--Left Navigation Ends here-->
        </div>
        <!--end left -->

        <!--start middle -->
        <div id="big_right">
            <!--start inside_middle -->
            <div id="inside_big_right">

                <div class="middle_top_box">
                    <div class="bigmenu">
                        <!--User Menu Starts here-->
                        <?php echo $user_menu; ?>
                        <!--User Menu Ends here-->
                    </div>
                </div>

                <!---------------------------------------content Start--------------------------------------->
                <form name="frm" id="frm" method="post" action="<?php echo site_url('group/create'); ?>"
                      onsubmit="return validateNewGroupCreation();">
                <div class="inside_page_content">
                    <div style="background-color: #F6F5F5;width:727px;height: 38px;">
                        <table>
                            <tr>
                                <td colspan="3" style="padding-right: 295px;padding-top:10px;color: #7B7B7D">Group
                                    Dashboard:&nbsp;<a href="<?php echo $base_url?>group/create"><span
                                            style="color:#0083CD;font-weight:bold">Create
                                     Groups</span></a>&nbsp;|&nbsp;<a href="<?php echo $base_url?>group/my"><span
                                            style="color:
                                     #1A93D2">My
                                            Groups</span></a> </td>
                                <td colspan="2" style="float: right;padding-top:10px;color: #7B7B7D">Mature Content is
                                    <a style="color:#0B8DD1 " href="">Viewable</a></td>
                            </tr>
                        </table>
                    </div>
                    <div style="color:#4D4D4D;font-weight: bold;padding-top:20px;padding-left: 10px;
                    padding-bottom:2px;border-bottom-style:
                           solid;border-width: 1px;border-color: #EAE6E6;width:715px;margin-bottom: 2px;">Group Details
                    </div>

                        <!--Options Starts -->
                        <div id="msgInGroup" class="error_display" style="display:none;" align="center"></div>
                        <div id="content_panel_group2">

                            <div id="profile_succ_msg" class="positive_msg_display"
                                 style="display:<?php if ($profile_edit_msg_flag != '1') {
                                     echo 'none';
                                 } ?>" align="center"><?php echo $err_msg[$profile_edit_msg_flag]; ?></div>
                            <div id="profile_err_msg" class="error_display"
                                 style="display:<?php if ($profile_edit_msg_flag < 2) {
                                     echo 'none';
                                 } ?>" align="center"><?php echo $err_msg[$profile_edit_msg_flag]; ?></div>


                                <table width="100%" border="0" cellspacing="0" cellpadding="0" style="margin-top:
                                13px;">
                                    <tr>
                                        <td  valign="top"
                                            class="small_text5_padding_left">Group
                                                Name: <span style="color: #ff0000;font-weight: bold">*</span>
                                        </td>
                                        <td><input name="group_name" id="group_name" type="text"
                                                               class="border10" maxlength="100"/>
                                            <br/>
                                            <!--                                            <span class="text_small3">What is the name of your Group?</span>-->

                                            <div class="extra_height"></div>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td width="30%" valign="top" class="small_text5_padding_left">Group
                                                Slogan: <span style="color: #ff0000;font-weight: bold">*</span>

                                        </td>
                                        <td width="70%"><input name="short_desc" id="short_desc" type="text"
                                                               class="border10" maxlength="100"/>
                                            <br/>
                                            <span class="text_small3">Give your group a short slogan to give
                                                member a quick insight of what your group is all about</br> (140
                                                characters remaining)</span>

                                            <div class="extra_height"></div>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td height="42" valign="middle" class="small_text5_padding_left">Group
                                                Category <span style="color: #ff0000;font-weight: bold">*</span>
                                        </td>
                                        <td><select name="group_category_id" id="group_category_id" class="other">
                                                <?php foreach ($res_group_category as $key => $val) { ?>
                                                    <option
                                                        value="<?php echo $val['group_category_id']; ?>"><?php echo $val['group_category_name']; ?></option>
                                                <?php } ?>
                                            </select></td>
                                    </tr>
                                    <tr>
                                        <td valign="top" class="small_text5_padding_left">Group Access
                                           <span style="color: #ff0000;font-weight: bold"> *</span>
                                        </td>
                                        <td>
                                            <table width="100%" border="0" cellspacing="0" cellpadding="0">
                                                <tr>
                                                    <td width="25" height="25" align="left" valign="top"><input
                                                            name="group_access" id="group_access" type="radio"
                                                            value="Public" checked="checked"/></td>
                                                    <td valign="top" class="small_text6">Public Group<br/>
                                                    </td>
                                                </tr>
                                                <tr><td colspan="5"><small>No invitation is required to join this group
                                                    </small></td></tr>
                                                <tr><td>&nbsp;</td></tr>
                                                <tr>
                                                    <td height="25" align="left" valign="top"><input name="group_access"
                                                                                                     id="group_access"
                                                                                                     type="radio"
                                                                                                     value="Private"/>
                                                    </td>
                                                    <td valign="top" class="small_text6">Private Group<br/>
                                                    </td>
                                                </tr>
                                                <tr><td colspan="5"><small>Invitation is required to join this group. Only
                                                            staff members may invite members to join this group
                                                        </small></td></tr>
                                                <tr><td>&nbsp;</td></tr>
                                                <tr>
                                                    <td height="25" align="left" valign="top"><input name="group_access"
                                                                                                     id="group_access"
                                                                                                     type="radio"
                                                                                                     value="Hidden"/>
                                                    </td>
                                                    <td valign="top" class="small_text6">Hidden Group<br/>
                                                    </td>
                                                </tr>
                                                <tr><td colspan="5"><small>This group only be viewed by members who belong to it.
                                                            Member must be sent an invitation from a staff member to
                                                            be able to access it.
                                                        </small></td></tr>
                                                <tr><td>&nbsp;</td></tr>
                                            </table>
                                        </td>
                                    </tr>
                                    </table></div>
                                    <div class="grp_permission">Group
                           Permissions
                    </div>
                                    <div id="content_panel_group3" style="background-color: #F6F5F5;width: 727px;">
                                    <table width="100%" border="0" cellspacing="2" cellpadding="2">
                                    <tr>
                                        <td valign="top" class="small_text5_padding_left">Staff
                                        Permissions:</br>
                                        (Admin)
                                        </td>
                                        <td>
                                            <table width="100%" border="0" cellspacing="0" cellpadding="0">
                                                <tr>
                                                    <td width="30%" class="small_text7">Comment Removal:</td>
                                                    <td class="small_text7"><select name="staff_remove_comment"
                                                                                    id="staff_remove_comment"
                                                                                    class="comment_border1">
                                                            <option value="0">Disallow comment Removal</option>
                                                            <option value="1" selected="selected">Allow comment
                                                                Removal
                                                            </option>
                                                        </select></td>
                                                </tr>
                                                <tr>
                                                    <td class="small_text7">Affiliates:</td>
                                                    <td class="small_text7"><select name="staff_remove_picture"
                                                                                    id="staff_remove_picture"
                                                                                    class="comment_border1">
                                                            <option value="0">Disallow picture Removal</option>
                                                            <option value="1" selected="selected">Allow picture
                                                                Removal
                                                            </option>
                                                        </select></td>
