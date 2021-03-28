import os


def list_files(startpath):
    record = open('file_list.txt', 'w')
    for root, dirs, files in os.walk(startpath):
        level = root.replace(startpath, '').count(os.sep)
        dir_indent = "|   " * (level - 1) + "|-- "
        file_indent = "|   " * level + "|-- "
        if not level:
            line = '.'
            record.write(line + '\n')
            print(line)

        else:
            line = '{}{}'.format(dir_indent, root)

            # line='{}{}'.format(dir_indent, os.path.basename(root))

            print(line)
            record.write(line + '\n')
        for f in files:
            line = '{}{}'.format(file_indent, os.path.join(root, f))
            # line='{}{}'.format(file_indent, f)
            print(line)
            record.write(line + '\n')
        for dir_ in dirs:
            line = '{}*D*{}'.format(file_indent, os.path.join(root, dir_))
            print(line)
            record.write(line + '\n')

    record.close()


if __name__ == '__main__':
    list_files('.')
