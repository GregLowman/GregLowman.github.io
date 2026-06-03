"""Media organiser: builds neighbourhood folders, sorts photos/videos, rotates by exiftool metadata."""
import os
import shutil
import subprocess

# Set to the source directory containing your neighbourhood subfolders (e.g. the USB drive root)
starting_folder = ''

# Set to the destination directory where the organised folders will be created
ending_folder = ''

# Set to the full path of your local exiftool executable — download at https://exiftool.org/
sorting_software = ''

picture = 'P: '
video = 'V: '
insta = 'Rotation                        : 0'
youtube = 'Rotation                        : 270'
neighborhood_names = []
picture_captions = []
video_captions = []


def sort_videos():
    """
    This function goes through every video within the separate neighborhood's Video folders. While
    skimming through the videos it will determine the rotation status to decide if the video is meant
    for Instagram, or for YouTube. If the program has any discrepancies it will place the media into an
    Unknown folder for the user to decide the next action.
    :return:
    """

    for name in neighborhood_names:
        for file in os.listdir(f"{ending_folder}/{name}/Videos"):
            new_file = f"{ending_folder}\\{name}\\Videos\\{file}"
            output = subprocess.getoutput(f'cmd /c"{sorting_software} "{new_file}"')
            if insta in output:
                shutil.move(new_file, f"{ending_folder}\\{name}\\Videos\\InstaReels")
            elif youtube in output:
                shutil.move(new_file, f"{ending_folder}\\{name}\\Videos\\YouTube")
            else:
                shutil.move(new_file, f"{ending_folder}\\{name}\\Videos\\Unknown")
            print('*')


def csv_to_txt(caption_name):
    """
    A function dedicated to pulling the text from a csv file (primarily excel)
    and putting those individual strings into their respective folders. Strings
    are to be seperated by either pictures or videos.

    :param caption_name: The file path to the file containing the csv text.
    """
    with open(caption_name, encoding='utf-8-sig', newline='') as captions:
        for x in captions:
            if picture in x:
                picture_captions.append(x[3:].strip('\r\n'))
            elif video in x:
                video_captions.append(x[3:].strip('\r\n'))


def sort():
    """
    This function sorts through all the files in the starting directory.
    Depending on the file extension, it will decide which of the new folders to copy it over to.
    If the file is a csv, it will convert it to text and then write it in the appropriate folder.
    """
    for z in neighborhood_names:
        picture_folder = os.path.join(ending_folder, z, "Pictures")
        video_folder = os.path.join(ending_folder, z, "Videos")
        picture_caption_folder = os.path.join(ending_folder, z, "Picture_Captions")
        video_caption_folder = os.path.join(ending_folder, z, "Video_Captions")
        path = f"{starting_folder}/{z}"

        for file in os.listdir(path):
            old_file = f"{path}/{file}"
            if '.jpg' in file:
                shutil.move(old_file, picture_folder)
            elif '.MP4' in file:
                shutil.move(old_file, video_folder)
            elif '.csv' in file:
                csv_to_txt(f"{path}/{file}")

        os.chdir(picture_caption_folder)
        for x in picture_captions:
            with open(f"{x}.txt", 'w') as pictures:
                print(x, file=pictures)

        os.chdir(video_caption_folder)
        for y in video_captions:
            with open(f"{y}.txt", 'w') as videos:
                print(y, file=videos)


def build_folders():
    """
    A function used to build folders in a new directory for all new files
    to be organised into. If the pathway already exists, the command will
    be passed over.
    """
    for x in os.listdir(starting_folder):
        neighborhood_names.append(x)
    for x in neighborhood_names:
        main_folder = os.path.join(ending_folder, x)
        picture_caption_folder = os.path.join(ending_folder, x, "Picture_Captions")
        video_caption_folder = os.path.join(ending_folder, x, "Video_Captions")
        picture_folder = os.path.join(ending_folder, x, "Pictures")
        video_folder = os.path.join(ending_folder, x, "Videos")
        insta_reel_folder = os.path.join(ending_folder, x, "Videos", "InstaReels")
        youtube_folder = os.path.join(ending_folder, x, "Videos", "YouTube")
        unknown_folder = os.path.join(ending_folder, x, "Videos", "Unknown")

        path_list = [
            ending_folder, main_folder, picture_caption_folder,
            video_caption_folder, picture_folder,
            video_folder, insta_reel_folder, youtube_folder, unknown_folder
        ]

        for path in path_list:
            try:
                os.mkdir(path)
            except FileExistsError:
                pass


def delete_empty():
    """
    Primary function is to simply delete empty folders once all the files have been moved.
    """
    for name in neighborhood_names:
        shutil.rmtree(f"{starting_folder}/{name}")


def run():
    build_folders()
    sort()
    sort_videos()
    delete_empty()


if __name__ == '__main__':
    run()
