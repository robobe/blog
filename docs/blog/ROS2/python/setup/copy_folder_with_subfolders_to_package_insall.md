---
title: ROS2 Python package, copy folder and sub folders to package install 
tags:
    - ros2
    - setup.py
    - python
ros:
    - setup.py
---

```python title="setup.py" linenums="1" hl_lines="1"
import os
from glob import glob
from setuptools import setup

package_name = 'myrobot_gazebo'

data_files=[
        ('share/ament_index/resource_index/packages',['resource/' + package_name]),
        ('share/' + package_name, ['package.xml']),
    ]


def package_files(data_files, directory_list):
    paths_dict = {}
    for directory in directory_list:
        for (path, directories, filenames) in os.walk(directory):
            for filename in filenames:
                file_path = os.path.join(path, filename)
                install_path = os.path.join('share', package_name, path)
                if install_path in paths_dict.keys():
                    paths_dict[install_path].append(file_path)
                else:
                    paths_dict[install_path] = [file_path]

    for key in paths_dict.keys():
        data_files.append((key, paths_dict[key]))

    return data_files


setup(
    name=package_name,
    version='0.0.0',
    packages=[package_name],
    data_files=package_files(data_files, ['models/', 'launch/', 'worlds/']),
    install_requires=['setuptools'],
    zip_safe=True,
    maintainer='ros',
    maintainer_email='ros@todo.todo',
    description='TODO: Package description',
    license='TODO: License declaration',
    tests_require=['pytest'],
    entry_points={
        'console_scripts': [
        ],
    },
)
```

---

## Reference
- [How to copy folders with subfolders to package installation path?](https://answers.ros.org/question/397319/how-to-copy-folders-with-subfolders-to-package-installation-path/)