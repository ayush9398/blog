---
layout: post
title: "GSoC 2020 @ Pitivi: Work Product"
date: 2020-07-05 14:00
summary: A summary to what's been done up until now.
category: pitivi
---

# Overview

My GSoC 2020 internship project was improving the usability of Pitivi's Render dialog. Below is a detailed summary of the work done during the last three months.

# Refactoring the Render Presets’ selection

The previous UI for selecting a render preset was being constructed dynamically. The same mechanism is used to also construct the audio and video selection preset UI in the project settings dialog. 

Can you even notice where the render Preset option is in all the clutter?

<p align="center">
    <img src="{{ site.baseurl }}/assets/img/render-dialog-old.png">
    <p style="font-size: 10px;" align="center"> Old Render Dialog-1</p>
</p>

We decided to move forward with a button which shows the current preset. When clicked, it opens a Gtk.Popover which lists the available presets. The presets listed in the popover include a relevant icon and an informative summary, making it an easy choice for the user. Thus I fixed issue #1813.

We mostly cared about rendering a project to be uploaded to an online sharing service such as YouTube, Vimeo, etc., so there are not many other options at the moment.

A custom icon is used for Custom profiles.

<p align="center">
    <img src="{{ site.baseurl }}/assets/img/render-dialog-new2.png">
    <p style="font-size: 10px;" align="center"> Updated Render Dialog with popover</p>
</p>

Through multiple iterations, we fine-tuned the UI so it looks nice and clear, improving the User Experience.

<b>MR:</b> [link](https://gitlab.gnome.org/GNOME/pitivi/-/merge_requests/306)

<b>MR status:</b> Merged.

# Addition of path property in Gstreamer Encoding-Target

Previously when a render profile was deleted, it was just marked as such. While at it, I took the opportunity to properly delete them. Unfortunately the path of the file where a GstPbutils.EncodingTarget object originates was not available.

I added a new `path` property to GstPbUtils.EncodingTarget and populated it when the object is saved or loaded.

<b>MR:</b> [link](https://gitlab.freedesktop.org/gstreamer/gst-plugins-base/-/merge_requests/714)

<b>MR status:</b> Merged.

# Hiding the advanced render UI in a new "Advanced" expander

The many settings displayed on the render dialog were intimidating to both new and seasoned users. Since many will never be interested in the advanced settings, I introduced an expander which hides the detailed settings of rendering dialog, at the same time keeping them easily accessible. 

Also, I moved the Folder and Filename sections at the bottom, to give more prominence to the render preset which is now at the top. I made the UI follow the GNOME Visual layout for an attractive and intuitive design.

<b>MR:</b> [link](https://gitlab.gnome.org/GNOME/pitivi/-/merge_requests/319)

<b>MR status:</b> Merged.

# Addition of Quality selection for supported encoders

In the video rendering process, there is a tradeoff between quality of the rendered video and the size of the video and the time it takes to render. If the user requires the video to be in high quality then the size of the video also increases.

To simplify the user's choice, a Gtk.Scale widget has been introduced for specifying the desired render quality. The quality setting affects different parameters for different encoders, but this is done in the background.

<p align="center">
    <img src="{{ site.baseurl }}/assets/img/render_settings_quality_1.png">
    <p style="font-size: 10px;" align="center"> Updated Render Dialog with Quality Scale.</p>
</p>

<p align="center">
    <img src="{{ site.baseurl }}/assets/img/render_settings_quality_2.png">
    <p style="font-size: 10px;" align="center"> Updated Render Dialog with Quality Scale -2.</p>
</p>

<b>MR:</b> [link](https://gitlab.gnome.org/GNOME/pitivi/-/merge_requests/323)

<b>MR status:</b> Work in Progress.

# Work to be done

Merge request !323 is still being reviewed in the final stages, and shall be merged soon.

We can add more presets, such as high-quality archiving to be able to dispose of the original video material.

We can show a summary of the render settings so the user can quickly check them and enter in the Advanced settings expander if something looks bad.
